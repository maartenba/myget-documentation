# Samples

Theory is nice, but it's always good to see some practical samples of implementing a web hook receiver for MyGet.

<p class="alert alert-success">
<strong>Tip:</strong> The <a href="https://github.com/aspnet/WebHooks">Microsoft ASP.NET WebHooks</a> library makes it easy to implement MyGet web hooks. It comes with an event handler and strong-typed events that allow building integrations with MyGet in an easy manner.
</p>

## Implementing custom package retention using webhooks

MyGet offers [retention policies](todo) that run whenever a package is added to a feed. These retention policies offer some options on when a package can be automatically removed from a feed, but it may be useful to implement a custom retention policy that is triggered [when a package is added](webhooks.md#package-added).

<p class="alert alert-info">
<strong>Note:</strong> Core for this example is <a href="https://github.com/MyGet/webhooks-custom-retention">available on GitHub</a>.
</p>

We'll first need something that can run our custom logic whenever a webhook event is raised. This can be an ASP.NET MVC, Web API, NancyFx or even a PHP application. In this case, let’s go with an ASP.NET Web API controller. We want to be triggered on POST when a package added event is raised.

{% method %}
{% sample lang="csharp" %}
```csharp
// POST /api/retention
public async Task<HttpResponseMessage> Post([FromBody]WebHookEvent payload)
{
    // The logic in this method will do the following:
    // 1) Find all packages with the same identifier as the package that was added to the originating feed
    // 2) Enforce the following policy: only the 5 latest (stable) packages matching the same minor version may remain on the feed. Others should be removed.
    string feedUrl = payload.Payload.FeedUrl;

    // Note: the following modifies NuGet's client so that we authenticate every request using the API key.
    // If credentials (e.g. username/password) are preferred, set the NuGet.HttpClient.DefaultCredentialProvider instead.
    PackageRepositoryFactory.Default.HttpClientFactory = uri =>
    {
        var client = new NuGet.HttpClient(uri);
        client.SendingRequest += (sender, args) =>
        {
            args.Request.Headers.Add("X-NuGet-ApiKey", ConfigurationManager.AppSettings["Retention:NuGetFeedApiKey"]);
        };
        return client;
    };

    // Prepare HttpClient (non-NuGet)
    var httpClient = new HttpClient();
    httpClient.DefaultRequestHeaders.Add("X-NuGet-ApiKey", ConfigurationManager.AppSettings["Retention:NuGetFeedApiKey"]);

    // Fetch packages and group them (note:  only doing this for stable packages, ignoring prerelease)
    var packageRepository = PackageRepositoryFactory.Default.CreateRepository(feedUrl);
    var packages = packageRepository.GetPackages().Where(p => p.Id == payload.Payload.PackageIdentifier).ToList();
    foreach (var packageGroup in packages.Where(p => p.IsReleaseVersion())
        .GroupBy(p => p.Version.Version.Major + "." + p.Version.Version.Minor))
    {
        foreach (var package in packageGroup.OrderByDescending(p => p.Version).Skip(5))
        {
            await httpClient.DeleteAsync(string.Format("{0}api/v2/package/{1}/{2}?hardDelete=true", feedUrl, package.Id, package.Version));
        }
    }

    return new HttpResponseMessage(HttpStatusCode.OK) { ReasonPhrase = "Custom retention policy applied." };
}
```
{% endmethod %}

Once we have this in place and are hosting it somewhere, we can configure the webhook on our MyGet feed.

On our MyGet feed, we can create a new webhook. It should send application/json for the package added event to the URL where we deployed the above code.

![Create webhook in MyGet](assets/create-webhook.png)

When this hook now triggers, we will be retaining just the 5 latest minor versions of a package (ignoring prereleases).

## Automatically strong name signing NuGet packages

<p class="alert alert-info">
<strong>Note:</strong> Core for this example is <a href="https://github.com/MyGet/webhooks-sign-package">available on GitHub</a>.
</p>

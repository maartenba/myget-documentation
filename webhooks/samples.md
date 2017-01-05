# Samples

Theory is nice, but it's always good to see some practical samples of implementing a web hook receiver for MyGet.

<p class="alert alert-success">
<strong>Tip:</strong> The <a href="https://github.com/aspnet/WebHooks">Microsoft ASP.NET WebHooks</a> library makes it easy to implement MyGet web hooks. It comes with an event handler and strong-typed events that allow building integrations with MyGet in an easy manner.
</p>

## Implementing custom package retention using webhooks

MyGet offers [retention policies](todo) that run whenever a package is added to a feed.

<p class="alert alert-info">
<strong>Note:</strong> Core for this example is <a href="https://github.com/MyGet/webhooks-custom-retention">available on GitHub</a>.
</p>

## Automatically strong name signing NuGet packages

<p class="alert alert-info">
<strong>Note:</strong> Core for this example is <a href="https://github.com/MyGet/webhooks-sign-package">available on GitHub</a>.
</p>

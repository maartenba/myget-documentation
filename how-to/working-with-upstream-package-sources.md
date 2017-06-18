# Working with upstream package sources

Package sources play a key role in a professional approach towards Package Management. MyGet gives you the option to specify one or more package sources for a feed. 

**Q: Why use package sources?**

* Upstream package sources make it easy to pull in packages from other package sources onto your downstream MyGet feeds. 
* You can also target these package sources to push packages upstream from your MyGet feeds.
* Any configured package source on a MyGet feed will be made available to you in MyGet Build Services without having to commit any credentials or secrets in your source repository.

Before diving into some practical scenarios, let's make sure we are clear in terms of terminology. The following Q&A should help you with that in a rather poetic way.

**Q: I'm confused about what "upstream" means in the context of package sources. What is upstream?**

Poetic answer:

> _Consider the direction in which packages are flowing from a given package source to an ocean of consumers._
> 
> _Your package can have dependencies "upstream", to packages on another feed._
> _From the point of view of those dependencies, the depending package is located "downstream"._
> _When a user consumes the downstream package, it will also fetch the upstream dependencies._
> 
> _The consumer, however, is only allowed to fetch or query those upstream packages if the feed he's talking to (downstream) is also configured to proxy the upstream package source._

## Adding a package source to your MyGet feed

By default, MyGet feeds have the public, central repositories configured for each package type. This includes:

* NuGet: https://www.nuget.org/api/v2
* Bower: https://bower.herokuapp.com
* npm: http://registry.npmjs.org
* Maven: https://repo1.maven.org/maven2

To configure an additional package source for your MyGet feed, navigate to _Feed Settings > Package Sources_. Then click _Add Package Source_ and select the package source type you want to add.

![](/assets/add package source button.png)

A dialog will prompt your for package source information and will also expose a few common presets for you to take advantage of.

If you have any access privileges to other MyGet feeds, you will see those in the MyGet Feeds presets, so you can easily build a chain of package sources to facilitate a [package promotion flow](/how-to/working-with-upstream-package-sources.md#using-a-feed-as-a-staging-area-push-upstream).

![](/assets/add package source - MyGet preset.png)

If you select another private MyGet feed you have access to as an upstream package source, there's no need to provide credentials to be able to restore packages from it on MyGet Build Services. MyGet will impersonate your user account when authenticating against that upstream feed.

## Adding a package from another package source

You can easily add packages to your MyGet feed originating from another package source, such as nuget.org, nmpjs.org, etc. This is using the feed's configured package sources under the hood. If you want to add a package from another feed onto your MyGet feed, the other feed needs to be configured as a package source to that feed.

Adding a package from an upstream package source can happen in three ways: manually, by reference (proxying), or by value (mirroring).
* **Manually**: you can add packages from an upstream package source to your feed manually by using the _Add Package_ button you will find under your feed's _Packages_ page. 

  ![](/assets/add package button.png)

  Select _From Feed_ in the dialog that prompts.

  ![](/assets/add package from feed.png)

* **Proxying**: the package metadata is copied to the MyGet feed, the package itself remains hosted on the upstream package source. When querying the package, we call the upstream package source to fetch the package.
* **Mirroring**: the package metadata and the package itself are copied onto the MyGet feed. When querying the package, we server the package directly and don't use the upstream packages source. Mirroring of a package version happens upon the first request for that given package version.

Configuring upstream package sources on your MyGet feed unlocks quite a few integration scenarios and automation opportunities!

![](/assets/package source compatibility.png)

### Proxy packages from another package source

You can configure a package source to proxy upstream packages through your MyGet feed to your feed consumers. Proxying makes it easy to have a single MyGet feed aggregate packages from multiple sources. Package consumers need only to configure a single MyGet feed, and all packages available on upstream, proxied package sources will become available to them.

Benefits:
* upstream packages do not count against your MyGet storage quota

Drawbacks:
* every package request will incur additional latency as opposed to storing the package onto the MyGet feed

<p class="alert alert-warning">
<strong>Warning!</strong> Avoid configuring multiple package source proxies on a single feed, or in a chain of feeds, as this will magnify the disadvantages, and result in very slow feed response times.
</p>

The following diagram illustrates the effects of package source proxying.

![](/assets/package source - proxying.png)

## Mirror packages from another package source

You can configure a package source to mirror upstream packages onto your MyGet feed. This configuration is similar to package proxying, but takes it one step further.

Whenever someone requests a particular package from your MyGet feed for the first time, MyGet will query the upstream package source and copy the package onto the MyGet feed.

Benefits:
* No additional latency (except for the first hit that triggers the package mirroring)
* Protected against upstream package source availability issues
* Protected against upstream package removal

Drawbacks:
* mirrored packages count towards your MyGet storage quota (you can always upgrade your subscription or <a href="mailto:support@myget.org">request a quote</a>!)

The following diagram illustrates the effects of package source mirroring.

![](/assets/package source - mirroring.png)

## Using a MyGet feed as a staging area (before pushing upstream)

TODO

## Using upstream package sources on MyGet Build Services

<p class="alert alert-info">
    Applies to: <strong>NuGet, NPM, PHP Composer</strong>
</p>

Package sources for a feed are also available during build. This can be useful in the following scenarios:

* An additional package source is needed during build. MyGet will make the package source available during build if it has been added to the feed's package sources.
* If you have a private feed requiring authentication but do not wish to add credentials to source control, credentials can be added to the feed's package source. These credentials will be available during build and allow you to consume a protected feed with ease.

<p class="alert alert-info">
    Applies to: <strong>NuGet</strong>
</p>

* The API key for a package source is also transferred to the build server. This means during a build, you can call into [`nuget.exe push`](https://docs.microsoft.com/en-us/nuget/tools/nuget-exe-cli-reference#push) and push packages to configured package sources.
* If you want to make use of [`nuget.exe push`](https://docs.microsoft.com/en-us/nuget/tools/nuget-exe-cli-reference#push) in a build script without having to specify the `-Source` parameter. This requires a default package source to be defined.

<p class="alert alert-info">
    Applies to: <strong>npm</strong><br/>
    We strongly suggest to <i>proxy</i> registry.npmjs.org to be able to run `npm install` during build, as npm will default to the MyGet feed as the default registry.
</p>

### Setting default package sources to be used on a MyGet feed's build services

<p class="alert alert-info">
    Applies to: <strong>NuGet</strong>
</p>

The `NuGet.config` file on our build agents is configured using NuGet's defaults, enriched with all NuGet package sources configured for a feed. Based on these defaults, the following conventions are active:

* The default package source is set to `(Aggregate Source)`, meaning all feeds will be queried for packages in the order defined in the feed's package sources.
* The default push source (when using `nuget push` without the `-Source` parameter) is NuGet.org.

Both of these conventions can be overridden by editing the build source configuration.
# Working with upstream package sources

Package sources play a key role in a professional approach towards Package Management. Upstream package sources make it easy to pull in packages from other package sources onto your downstream MyGet feeds. On the other hand, you can also target these package sources to push packages upstream from your MyGet feeds.

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

## Adding a package from another package source

You can easily add packages to your MyGet feed originating from another package source, such as nuget.org, nmpjs.org, etc. This is using the feed's configured package sources under the hood.

By default, MyGet feeds have the public, central repositories configured for each package type. This includes:

* NuGet: https://www.nuget.org/api/v2
* npm: http://registry.npmjs.org/
* Maven: https://repo1.maven.org/maven2/

The _Add Package From Feed_ dialog shows 

## Proxy packages from another package source

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
# NuGet \(.NET\)

TODO (inspiration: http://docs.myget.org/docs/walkthrough/getting-started-with-nuget)

## Connecting to a NuGet feed

public feed, private feed with basic auth, pre-authenticated feed URL

### Find our feed URL

#### Private feed

Private feeds are only accessible to the feed owner, and to whomever the feed owner granted sufficient privileges. When we need to connect to a private feed we don't own, we may need to ask the feed owner to invite us to the feed.

> ### Hint
> We can find out how to invite users [here](../inviting-users-to-a-feed.md)

![Feed details](assets/feed-details.png)

> ### Hint
> We support [Visual Studio](#visual-studio), [JetBrains Rider](#jetbrains-rider), the [NuGet CLI](#nuget-cli), [dotnet CLI](#dotnet-cli) and [Paket](#paket).

#### Public feed

There are two types of public feeds we can connect to. A public feed we own and one from the gallery. The only real difference here, is where to find the URL of the feed.

MyGet feeds have multiple endpoints, and each one is specific to a particular package type and protocol. Pick the NuGet endpoint URL that matches the protocol version you want to use (e.g. NuGet v3), and use that to configure the feed endpoint in your favorite NuGet client.

#### Gallery feed

After browsing the list of feeds on the [MyGet Gallery](https://myget.org/gallery) (or on the MyGet Enterprise Gallery), we can get its connection details using the **Connect to feed** button. This will open a dialog where we can find the various endpoints for this feed.

![Gallery feed details](assets/gallery-feed.png)
![Gallery feed URL](assets/connect-gallery-feed.png)

We will need the NuGet V3 URL, so let's copy it for later use.

### Visual Studio

#### Public feed

If we don't know where to find our feed URL check the [Find our feed URL](#find-our-feed-url) section.

#### Private feed

#### Credential Provider for Visual Studio

inspiration: http://docs.myget.org/docs/reference/credential-provider-for-visual-studio but needs to be nicer

### JetBrains Rider

#### Public feed

If we don't know where to find our feed URL check the [Find our feed URL](#find-our-feed-url) section.

#### Private feed

### NuGet CLI

#### Public feed

If we don't know where to find our feed URL check the [Find our feed URL](#find-our-feed-url) section.

#### Private feed

## Creating NuGet/.NET Core packages

could have links to the NuGet documentation

## Publishing to MyGet

## Troubleshooting


### Package not found during package restore

When working with our own feed, whether private or public, chances are we want to consume more than just that feed. When using our MyGet feed and the NuGet.org feed simultaneously, an interesting error may occur during package restore.

   Unable to find version xxxx of package yyyy

The reason this happens is because the NuGet command line, the NuGet Visual Studio Extension and the NuGet PoourShell Console all have a configuration option specifying which package source to install from. When this setting is changed to one specific feed, other feeds will be ignored and the error above will be shown during package restore.

The solution is very simple: we can set the active package source to aggregate in Visual Studio, or simply configure NuGet to always use the aggregate package source for the current project. NuGet has an inheritance system for NuGet.config files, where the NuGet.config file closest to the solution file gets the last say. If we add the following NuGet.config file next to the solution file for our project, we should be fine:

```xml
  <?xml version="1.0" encoding="utf-8"?>
    <configuration>
      <activePackageSource>
         <add key="All" value="(Aggregate source)" />
      </activePackageSource>
    </configuration>
```

We can take this one step further and instead of configuring our MyGet feed globally for our system (and requiring other devs on our team to do the same), why not distribute a NuGet.config along with the sources?

```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <packageRestore>
      <add key="enabled" value="True" /><add key="automatic" value="True" />
    </packageRestore>
    <packageSources>
      <add key="nuget.org" value="https://www.nuget.org/api/v2/" />
      <add key="MyGet" value="https://www.myget.org/F/chucknorris/" />
    </packageSources>
    <disabledPackageSources />
    <activePackageSource>
      <add key="All" value="(Aggregate source)" />
    </activePackageSource>
  </configuration>
```

This really makes working with multiple feeds a breeze. But we can go even further and use only MyGet, proxying packages from NuGet.org along the way. For more info on how that works, check the [documentation on upstream package sources](/docs/reference/package-sources#Scenario_-_Proxying_upstream_feeds_and_packages).

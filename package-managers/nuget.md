# NuGet \(.NET\)
TODO (inspiration: http://docs.myget.org/docs/walkthrough/getting-started-with-nuget)


## Connecting to a NuGet feed
public feed, private feed with basic auth, pre-authenticated feed URL


### Find your feed URL

#### Public feed
There are two types of public feeds you can connect to. A public feed you own and one from the gallery. The only real difference here, is where to find the URL of the feed.

With this URL you can connect to the feed using your favorite tool, which could be [Visual Studio](#visual-studio), [JetBrains Rider](#jetbrains-rider) or the [NuGet-CLI](#nugetexe)


##### Gallery feed
When connecting to a gallery feed you first click on the feed you want to connect to and there click on the "Connect to feed" button.

![Gallery feed details](assets/gallery-feed.png)

A dialog opens where you will once again find your 'NuGet V3' URL.

![Gallery feed URL](assets/connect-gallery-feed.png)

With this URL you can connect to the feed using your favorite tool, which could be [Visual Studio](#visual-studio), [JetBrains Rider](#jetbrains-rider) or the [NuGet-CLI](#nugetexe)

##### Private feed
To consume private feeds you need to get consume permissions from the feed owner or admin. When you have these rights you can navigate to the 'feed details' where you can find the 'NuGet V3' URL. 

![Feed details](assets/feed-details.png)

With this URL you can connect to the feed using your favorite tool, which could be [Visual Studio](#visual-studio), [JetBrains Rider](#jetbrains-rider) or the [NuGet-CLI](#nugetexe)


### Visual Studio

#### Public feed
If you don't know where to find your feed URL check the [Find your feed URL](#find-your-feed-url) section.

#### Private feed

#### Credential Provider for Visual Studio
inspiration: http://docs.myget.org/docs/reference/credential-provider-for-visual-studio but needs to be nicer


### JetBrains Rider

#### Public feed
If you don't know where to find your feed URL check the [Find your feed URL](#find-your-feed-url) section.

#### Private feed


### NuGet.exe

#### Public feed
If you don't know where to find your feed URL check the [Find your feed URL](#find-your-feed-url) section.

#### Private feed


## Creating NuGet/.NET Core packages
could have links to the NuGet documentation


## Publishing to MyGet


## Troubleshooting


### Package not found during package restore
When working with your own feed, whether private or public, chances are you want to consume more than just that feed. When using your MyGet feed and the NuGet.org feed simultaneously, an interesting error may occur during package restore.

	Unable to find version xxxx of package yyyy

The reason this happens is because the NuGet command line, the NuGet Visual Studio Extension and the NuGet PowerShell Console all have a configuration option specifying which package source to install from. When this setting is changed to one specific feed, other feeds will be ignored and the error above will be shown during package restore.

The solution is very simple: you can set the active package source to aggregate in Visual Studio, or simply configure NuGet to always use the aggregate package source for the current project. NuGet has an inheritance system for NuGet.config files, where the NuGet.config file closest to the solution file gets the last say. If you add the following NuGet.config file next to the solution file for your project, you should be fine:

	<?xml version="1.0" encoding="utf-8"?>
	<configuration>
	  <activePackageSource>
	    <add key="All" value="(Aggregate source)" />
	  </activePackageSource>
	</configuration>

We can take this one step further and instead of configuring your MyGet feed globally for your system (and requiring other devs on your team to do the same), why not distribute a NuGet.config along with the sources?

	<?xml version="1.0" encoding="utf-8"?>
	<configuration>
	  <packageRestore>
	    <add key="enabled" value="True" />
	    <add key="automatic" value="True" />
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

This really makes working with multiple feeds a breeze. But we can go even further and use only MyGet, proxying packages from NuGet.org along the way. For more info on how that works, check the [documentation on upstream package sources](/docs/reference/package-sources#Scenario_-_Proxying_upstream_feeds_and_packages).

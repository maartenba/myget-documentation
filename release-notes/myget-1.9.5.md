# MyGet 2014.2 Release Notes

MyGet 2014.2 was released on November 18, 2014.

## Major Features

It's been a while since we tagged another MyGet release, but here we are, 9 months after tagging v2014.1.  
We constantly ship and deploy improvements to our service so this v2014.2 basically aggregates everything we've done since then, combined into a single milestone.  
This release contains many exciting new features. We'd love to hear from you so [please send us your feedback](http://myget.uservoice.com/)!

* [Visual Studio Online integration](http://blog.myget.org/post/2014/05/12/Announcing-Visual-Studio-Online-integration.aspx)
* [MyGet now offered through the Microsoft Azure store!](http://blog.myget.org/post/2014/08/05/MyGet-now-offered-through-the-Microsoft-Azure-Store.aspx) \(use your MSDN!\)
* [Package mirroring is now enabled by default](http://blog.myget.org/post/2014/05/19/package-mirroring-is-now-enabled-by-default.aspx)
* [Build Status Badges](http://blog.myget.org/post/2014/01/15/Build-Status-Badges.aspx)
* [MyGet Web Hooks](http://blog.myget.org/post/2014/09/10/Introducing-MyGet-webhooks.aspx) \(see how we've built [a custom package retention rules sample](http://blog.myget.org/post/2014/10/16/Implementing-custom-package-retention-using-webhooks.aspx)\)
* [Package License Analysis](http://blog.myget.org/post/2014/06/03/Creating-a-license-report-for-your-NuGet-packages.aspx)
* [Package Update Notifications](http://blog.myget.org/post/2014/09/23/Notifications-let-you-know-when-a-package-is-updated.aspx)
* [Redesigned MyGet Documentation site](http://blog.myget.org/post/2014/03/03/MyGet-Documentation-site-redesigned.aspx)
* [MyGet Feeds now support Target Framework Filtering](http://blog.myget.org/post/2014/10/08/myget-feeds-now-support-target-framework-filtering.aspx)

### MyGet

* Improved status/error message when contributor fails pushing to a private feed on expired subscription plan
* [Add package from feed dialog now allows specifying Lowest/Highest/HighestPatch setting for dependency resolution](http://blog.myget.org/post/2014/05/05/Picking-the-right-dependency-version-adding-packages-from-NuGet.aspx)
* Support pre-authenticated feeds for clients that don't support basic authentication
* Support Visual Studio Online as a package source
* [Improved RSS feed-endpoint](http://blog.myget.org/post/2014/04/07/get-notified-of-feed-activity-through-rss.aspx) allowing you to receive feed activity notifications. Also enabled RSS auto-discovery on feed pages on the MyGet web site to facilitate detection of the RSS endpoint in the browser.
* [Configure a feed's Report Abuse URL](http://blog.myget.org/post/2014/08/18/Configure-a-feeds-Report-Abuse-URL.aspx)
* Support for NuGet 2.8.3

### MyGet Enterprise

* [Administrators can now configure password policies and account lockout settings](http://blog.myget.org/post/2014/04/25/Configuring-password-policies-and-account-lockout-using-MyGet-Enterprise.aspx)
* [Administrators can now configure IP white-listing for the Enterprise tenant](http://blog.myget.org/post/2014/11/13/IP-whitelisting-for-MyGet-Enterprise-customers.aspx)
* Administrators can now create users directly from within the administrative dashboard
* Administrators are now able to join feeds even when feed contributor quota is reached
* VSO, GitHub, CodePlex and BitBucket integrations are now also available for Enterprise tenants

### MyGet Build Services

* [Support for user-defined variables](http://blog.myget.org/post/2014/10/14/User-defined-environment-variables-in-MyGet-builds.aspx)
* [Built-in Support for GitVersion](http://docs.myget.org/docs/reference/build-services#GitVersion_and_Semantic_Versioning)
* [Add ability to push packages upstream directly from build artifacts](http://blog.myget.org/post/2014/06/26/Promoting-packages-generated-during-build.aspx)
* [Allow specifying which projects get built](http://blog.myget.org/post/2014/03/10/Specifying-which-projects-get-built-with-MyGet-Build-Services.aspx)
* [Configurable default upstream package source to push built artifacts to](http://blog.myget.org/post/2014/03/25/Setting-default-package-sources-during-build.aspx)
* Added support for XUnit 1.9.2
* Add `.fsproj` support for building and packaging F\# projects
* Add warning in build log when detecting NuGet manifests named `projectName.ext.nuspec` \(where `ext` is a known file extension such as `csproj`, `dll`, etc\). This breaks nuspec-project correlation during builds resulting in not picking up the nuspec during packaging of a project.
* Build time is now measured for each step and available in the build log
* Made build status API reporting optional

## Minor Tweaks and Bug Fixes

* Build Services: Builds now fail immediately for feeds that return a 4XX or 5XX status code
* Build Services: No longer ignore `*Test*.nuspec` files when packaging
* Build Services: Assembly Version Patching no longer fails to process files that contain Visual Studio regions
* Build Services: Delete web hook at GitHub / VSO when build source is deleted
* API: `nuget delete` is no longer case-sensitive on package ID
* Cloning gallery feeds now unpublishes the cloned feed from the gallery
* Allow updating the description of access tokens
* Support page - Ability to select the \(own\) feed related to the support request, which helps us provide even faster support! ;\)

In addition, this release also contains a lot of performance fixes, and we continue to work hard on improving your overall MyGet experience.  
If you feel strong about a missing feature or have an idea for further improvement, [please let us know](http://myget.uservoice.com/)! We build this for you!

_Happy packaging!_


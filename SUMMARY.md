# Summary

## Getting started
* [What is MyGet?](README.md)
* [Creating a MyGet feed \(repository\)](creating-a-myget-repository.md)
* [Inviting users to a feed](inviting-users-to-a-feed.md)
    * [Managing user permissions](inviting-users-to-a-feed.md#managing-user-permissions)
    * [Available feed privileges](inviting-users-to-a-feed.md#available-feed-privileges)
* [MyGet gallery](myget-gallery.md)
* [Frequently Asked Questions \(FAQ\)](frequently-asked-questions-faq.md)

## Package managers
* TODO [NuGet \(.NET\)](package-managers/nuget.md)
    * Connecting to a NuGet feed
        * Credential Provider for Visual Studio
    * Creating NuGet/.NET Core packages
    * Publishing to MyGet
	* [Troubleshooting](package-managers/nuget.md#troubleshooting)
    * Tips and tricks
        * [Migrating to MyGet](package-managers/tips-tricks/migrating-to-myget.md)
        * [Consume a private feed in TeamCity](package-managers/tips-tricks/consume-a-private-feed-in-teamcity.md)
        * [NuGet configuration inheritance](package-managers/tips-tricks/nuget-configuration-inheritance.md)
        * [Using Paket with MyGet](package-managers/tips-tricks/using-paket-with-myget.md)
        * [Packaging FSharp](package-managers/tips-tricks/packaging-fsharp.md)
* [Symbols and sources \(.NET\)](package-managers/symbols-and-sources.md)
    * [Publishing debugger symbols](package-managers/symbols-and-sources.md#publishing-debugger-symbols)
    * [Consuming debugger symbols](package-managers/symbols-and-sources.md#consuming-debugger-symbols)
    * [Troubleshooting](package-managers/symbols-and-sources.md#troubleshooting)
* TODO [Chocolatey \(Windows - machine\)](package-managers/chocolatey.md)
    * Connecting to a feed
    * Publishing to MyGet
* TODO [PowerShell \(Windows - machine\)](package-managers/powershell.md)
    * Connecting to a feed
    * Publishing a PowerShell Module to MyGet
* TODO [NPM \(Node.js\)](package-managers/npm.md)
    * Connecting to a NPM feed
    * Creating NPM packages
    * Publishing to MyGet
    * Scoped packages
* TODO [Bower \(JavaScript\)](package-managers/bower.md)
    * Connecting to a Bower feed
    * Creating Bower packages
    * Publishing to MyGet
* TODO [Maven \(Java\)](package-managers/maven.md)
    * Connecting to a Maven feed
        * Maven
        * Gradle
    * Creating Maven packages \(+ very short intro to build services\)
    * Publishing to MyGet
* TODO [VSIX](package-managers/vsix.md)
    * Connecting to a VSIX feed
    * Creating VSIX packages \(+ very short intro to build services\)
    * Publishing to MyGet

## How-to
* [Working with retention rules](how-to/package-retention-rules.md)
* TODO [Working with upstream package sources](how-to/working-with-upstream-package-sources.md)
    * [As a package proxy](how-to/working-with-upstream-package-sources.md#proxy-upstream-package-source)
    * [As a staging area \(push upstream\)](how-to/working-with-upstream-package-sources.md#using-a-feed-as-a-staging-area-push-upstream)
* TODO [Keeping projects up-to-date](how-to/keeping-projects-up-to-date.md)
    * Auto-updating packages
    * Getting package update notifications
* [Analyzing open-source licenses](how-to/license-analysis.md)
* [Package vulnerabilities](how-to/package-vulnerabilities.md)
* [Managing access tokens](how-to/access-tokens.md)
    * [Editing access tokens](how-to/access-tokens.md#editing-access-tokens)
    * [Scoped access tokens](how-to/access-tokens.md#scoped-access-tokens)

## Build services
* TODO What are build services?
* TODO Convention-based builds
    * For NuGet
    * For NPM
    * For VSIX
* TODO Build scripts
    * Example build script 1
    * Example build script 2
    * Example build script 3
* TODO Trigger builds automatically
    * GitHub webhook
    * BitBucket webhook
    * VSTS webhook
    * GitLab webhook
    * Generic webhook
* TODO Tips and tricks
    * Using NuGet command-line in build scripts
    * Using psake in build scripts
    * Building Chocolatey packages
    * Using VSTS Git with MyGet Build Services

## Web hooks
* [What are web hooks?](webhooks/webhooks.md)
* [HTTP POST web hooks](webhooks/webhooks.md#http-post-webhook)
    * Events
        * [Ping](webhooks/webhooks.md#ping)
        * [Package added](webhooks/webhooks.md#package-added)
        * [Package deleted](webhooks/webhooks.md#package-deleted)
        * [Package listed\/unlisted](webhooks/webhooks.md#package-listed-unlisted)
        * [Package pinned\/unpinned](webhooks/webhooks.md#package-pinned-unpinned)
        * [Package pushed](webhooks/webhooks.md#package-pushed)
        * [Build queued](webhooks/webhooks.md#build-queued)
        * [Build started](webhooks/webhooks.md#build-started)
        * [Build finished](webhooks/webhooks.md#build-finished)
    * [Samples](webhooks/samples.md)
        * [Implementing custom package retention using webhooks](webhooks/samples.md#implementing-custom-package-retention-using-webhooks)
        * [Automatic strong name signing for NuGet packages](webhooks/samples.md#automatic-strong-name-signing-for-nuget-packages)
* [Service-specific webhooks](webhooks/webhooks.md#service-specific-webhooks)
    * [Email webhook](webhooks/webhooks.md#email-webhook)
    * [HipChat webhook](webhooks/webhooks.md#hipchat-webhook)
    * [Slack webhook](webhooks/webhooks.md#slack-webhook)
    * [Microsoft Teams webhook](webhooks/webhooks.md#microsoft-teams-webhook)
    * [Twilio](webhooks/webhooks.md#twilio-webhook)
    * [Twitter](webhooks/webhooks.md#twitter-webhook)

## Enterprise
* [Management dashboard](myget-enterprise/management-dashboard.md)
    * [Statistics](myget-enterprise/management-dashboard.md#statistics)
    * [Accounts](myget-enterprise/management-dashboard.md#accounts)
        * [Registration](myget-enterprise/management-dashboard.md#registration)
        * [IP security](myget-enterprise/management-dashboard.md#ip-security)
        * [Login](myget-enterprise/management-dashboard.md#registration-and-login)
        * [Passwords](myget-enterprise/management-dashboard.md#passwords)
        * [Lockout](myget-enterprise/management-dashboard.md#lockout)
        * [Sessions](myget-enterprise/management-dashboard.md#sessions)
        * [Feed creation](myget-enterprise/management-dashboard.md#feed-creation)
    * [Users](myget-enterprise/management-dashboard.md#users)
        * [Creating a user](myget-enterprise/management-dashboard.md#creating-a-user)
        * [Deleting a user](myget-enterprise/management-dashboard.md#deleting-a-user)
        * [Manging user quota](myget-enterprise/management-dashboard.md#managing-user-quota)
    * [Feeds](myget-enterprise/management-dashboard.md#feeds)
    * [Analytics](myget-enterprise/management-dashboard.md#analytics)
    * [Gallery](myget-enterprise/management-dashboard.md#gallery)
    * [SMTP settings](myget-enterprise/management-dashboard.md#smtp-settings)
    * [Default quota](myget-enterprise/management-dashboard.md#default-quota)
* Identity providers
    * [ADFS integration](myget-enterprise/adfs-integration.md)
    * [Azure AD Integration](myget-enterprise/azure-ad-integration.md)
    * [Okta integration](myget-enterprise/okta-integration.md)

## Reference
* [Capturing traffic with Fiddler](reference/capturing-traffic-with-fiddler.md)
* [Feed endpoints](reference/feed-endpoints.md)
    * Package managers
        * [NuGet \(.NET\)](reference/feed-endpoints.md#nuget-compatible-feed-endpoints)
        * [Symbols and sources \(.NET\)](reference/feed-endpoints.md#symbol-server-endpoints)
        * [Chocolatey \(Windows - machine\)](reference/feed-endpoints.md#nuget-compatible-feed-endpoints)
        * [PowerShell \(Windows - machine\)](reference/feed-endpoints.md#nuget-compatible-feed-endpoints)
        * [NPM \(Node.js\)](reference/feed-endpoints.md#npm-compatible-feed-endpoints)
        * [Bower \(JavaScript\)](reference/feed-endpoints.md#bower-compatible-feed-endpoints)
        * [Maven \(Java\)](reference/feed-endpoints.md#maven-compatible-feed-endpoints)
        * [VSIX](reference/feed-endpoints.md#vsix-compatible-feed-endpoints)
    * Protocol-specific
        * [NuGet v2\/v3](reference/feed-endpoints.md#nuget-compatible-feed-endpoints)
        * [Symbols and sources](reference/feed-endpoints.md#symbol-server-endpoints)
        * [NPM](reference/feed-endpoints.md#npm-compatible-feed-endpoints)
        * [Bower](reference/feed-endpoints.md#bower-compatible-feed-endpoints)
        * [Maven](reference/feed-endpoints.md#maven-compatible-feed-endpoints)
        * [VSIX](reference/feed-endpoints.md#vsix-compatible-feed-endpoints)
    * [Private feed endpoints & authentication](reference/feed-endpoints.md#private-feed-endpoints-and-authentication)
    * [Feed State API](reference/feed-state-api-endpoint.md)

## Release notes
* [MyGet 2.2](release-notes/myget-2.2.md)
* [MyGet 2.1](release-notes/myget-2.1.md)
* [MyGet 2.0](release-notes/myget-2.0.md)
* [MyGet 1.9.5](release-notes/myget-1.9.5.md)
* [MyGet 1.9](release-notes/myget-1.9.md)
* [MyGet 1.8](release-notes/myget-1.8.md)
* [MyGet 1.7](release-notes/myget-1.7.md)
* [MyGet 1.6](release-notes/myget-1.6.md)
* [MyGet 1.5](release-notes/myget-1.5.md)
* [MyGet 1.4](release-notes/myget-1.4.md)


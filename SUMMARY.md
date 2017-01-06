# Summary

## Examples for doc writer
* [Source code](methods.md)
* [Notes, alerts and callouts](notesalertscallouts.md)

## Getting started
* [What is MyGet?](README.md)
* [Creating a MyGet feed (repository)](creating-a-myget-repository.md)
* [Inviting collaborators to a feed](inviting-collaborators-to-a-feed.md)
* MyGet gallery
* Frequently Asked Questions \(FAQ\)

## Package managers
* NuGet \(.NET\)
    * Connecting to a NuGet feed
        * Credential Provider for Visual Studio
    * Creating NuGet packages + .NET core
    * Publishing to MyGet
    * Tips and tricks
        * Migrating to MyGet
        * Consume a private feed in TeamCity
        * NuGet configuration inheritance
        * Package not found during package restore
        * Using Paket with MyGet feeds
        * Packaging FSharp
* Symbols and sources \(.NET\)
    * Publishing debugger symbols
    * Consuming debugger symbols
* Chocolatey \(Windows - machine\)
    * Connecting to a feed
    * Publishing to MyGet
* PowerShell \(Windows - machine\)
    * Connecting to a feed
    * Publishing a PowerShell Module to MyGet
* NPM \(Node.js\)
    * [Connecting to a NPM feed](connecting-to-a-npm-feed.md)
    * [Creating NPM packages](creating-npm-packages.md)
    * Publishing to MyGet
    * [Scoped packages](scoped-packages.md)
* Bower \(JavaScript\)
    * Connecting to a Bower feed
    * Creating Bower packages
    * Publishing to MyGet
* Maven \(Java\)
    * Connecting to a Maven feed
        * Maven
        * Gradle
    * Creating Maven packages \(+ very short intro to build services\)
    * Publishing to MyGet
* VSIX
    * Connecting to a VSIX feed
    * Creating VSIX packages \(+ very short intro to build services\)
    * Publishing to MyGet

## How-to
* [Working with retention rules](how-to/package-retention-rules.md)
* Working with upstream package sources
    * As a package proxy
    * As a staging area \(push upstream\)
* Keeping projects up-to-date
    * Auto-updating packages
	* Getting package update notifications
* Analyzing open-source licenses
* Package vulnerabilities
* Working with web hooks

## Build services
* What are build services?
* Convention-based builds
    * For NuGet
    * For NPM
    * For VSIX
* Build scripts
    * Example build script 1
    * Example build script 2
    * Example build script 3
* Trigger builds automatically
    * GitHub webhook
    * BitBucket webhook
    * VSTS webhook
    * GitLab webhook
    * Generic webhook
* Tips and tricks
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
* Feed endpoints
    * TODO Per package manager
    * TODO Feed state API

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


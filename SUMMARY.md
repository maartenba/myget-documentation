# Summary

## Examples for doc writer
* [Source code](methods.md)

## Getting started
* [What is MyGet?](README.md)
* [Creating a MyGet feed/repository](creating-a-myget-repository.md)
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
* Chocolatey \(Windows\/machine\)
    * Connecting to a feed
    * Publishing to MyGet
* PowerShell \(Windows\/machine\)
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

## Scenarios
* Working with retention rules
* Working with upstream package sources
    * As a package proxy
    * As a staging area \(push upstream\)
* Keeping projects up-to-date \(auto-update packages \/ notifications\)
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
* What are web hooks?
* HTTP POST web hooks
    * Samples
        * Samples from blog
        * ASP.NET Web API web hook receiver
* Service-specific webhooks
    * Email webhook
    * HipChat webhook
    * Slack webhook
    * Twilio
    * Twitter

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
* Capturing traffic with Fiddler
* Feed endpoints
    * Per package manager
    * Feed state API

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


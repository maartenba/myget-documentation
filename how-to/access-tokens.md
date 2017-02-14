# Managing access tokens

There are several credentials linked to your MyGet profile. Every user gets at least one the primary API key, which can be used when publishing packages with NuGet.exe,  NuGet Package Explorer, npm, Bower and so on. There's also a username and password for consuming private feeds from Visual Studio or a build server.

Additional access tokens can be generated [from your profile page](https://www.myget.org/profile/Me#!/AccessTokens). The primary API key can be regenerated and new tokens can be easily created or revoked.

* Access tokens can be given a short description: this will help keeping track of where you used the access token and revoke it if necessary.
* Access tokens can be scoped to allow access only to a specific feed - limiting the surcace area to which a given access token can push packages.
* Access tokens can be given an optional expiration date, after which the token will no longer be valid.

Access tokens can be used for all authentication purposes, except logging into the MyGet.org website. They can be used when pushing to your MyGet feed or as an alternate password when authenticating against a private feed.

![Managing access tokens](assets/access_token_management.png)

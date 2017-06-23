# Auto updating packages

MyGet feeds can automatically fetch package updates made available through the upstream package sources.

When adding or editing a package source, we can enable this behaviour per package source, as well as an interval when MyGet should check for updates.

![](/assets/add package source options.png)

The following options are available:
* **E-mail me when package updates are available**: Sends an e-mail to the specified recipient(s) when package updates are available on the upstream package source.
* **Include prerelease versions**: By default, MyGet will only consider stable packages. When enabled, we will also check prerelease packages from the upstream package source.
* **Automatically update packages to their latest versions**: Enables the behaviour of automatically updating packages from the package source.
* **Update interval**: Depending on your subscription plan, we can specify how often MyGet should check for updates (up to every 30 minutes on a [Professional subscription](https://www.myget.org/plans))
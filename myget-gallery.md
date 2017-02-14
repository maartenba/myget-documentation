# MyGet Gallery

The [MyGet Gallery](https://www.myget.org/gallery) is the perfect place to promote your feeds and their packages. If you are looking to publish packages to one or more staging or CI feeds, you may as well make them discoverable!

On [MyGet.org](https://www.myget.org), feeds can be discovered [in the gallery](https://www.myget.org/gallery) by anyone out there. When working in an [Enterprise plan](https://www.myget.org/enterprise), the gallery can be used to promote feeds to other development teams or customers.

Publishing your feed in the MyGet Gallery allows people to search for it without knowing the exact URL, whilst allowing you to provide some additional information about the feed or your project using the feed's details page in the gallery.

## Requirements

There are a basic set of requirements that must be met before you can publish your feed in the MyGet gallery.

* Only public and community feeds can be listed in the MyGet Gallery (on the [Enterprise plan](/myget-enterprise/management-dashboard.md) other feed types can be published for subsets of users)
* Your feed may not have the default (sample) readme text: it's meaningless and we encourage you to provide some meaningful message to your feed consumers. You could also leverage your existing readme file from your project's GitHub repository instead.
* Your feed may not have the default (sample) feed description on the Feed Details page.

## Publishing your feed in the MyGet Gallery

If you meet the above requirements, all you need to do to publish your feed in the MyGet Gallery is to click on the **'Yes, list my feed in the Gallery.'** checkbox on the feed's Gallery settings page.

![Listing a feed in the gallery](assets/gallery_publish_checkbox.png)
 
Click the **Save** button to update your settings.

<p class="alert alert-info">
Note that it may take up to 15 minutes for your feed to appear in the MyGet Gallery due to caching.
</p>

## Adding an readme using markdown

To provide your feed consumers with some context on the feed, or disclaimer, or project-related information, you may want to add a readme to your feed.
The readme can be written in Markdown, or you can simply reference an existing readme from your GitHub repository.

To link an existing readme from GitHub, click on the **import from GitHub** link and select an entry in the popup dialog that appears by clicking on the **Use This** button next to it.

## Setting a feed icon

![Import readme from GitHub](assets/gallery_link_readme_from_github.png)

Finally, you can also add an icon to make your feed easily recognizable in the gallery listing by entering an URL to an image, or by uploading a JPG, GIF or PNG file of choice. Optimal icon resolution is 50 by 50 pixels.

![Add feed icon](Images\gallery_add_feed_icon.png)
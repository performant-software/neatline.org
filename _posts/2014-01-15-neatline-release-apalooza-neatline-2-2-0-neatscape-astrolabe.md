---
title: 'Neatline release-apalooza: Neatline 2.2.0, Neatscape, Astrolabe'
author: dm4fn
excerpt: 'Today we&rsquo;re excited to announce the release of Neatline 2.2.0! This is a big update that ships out a cluster of features and fixes that address a couple of rough spots identified by users over the course of the last couple months. 2.2.0 focuses on improvements in two areas &ndash; first, we&rsquo;ve overhauled the workflows&hellip;. <a href="http://www.scholarslab.org/announcements/neatline-2-2-0/">More.</a>'
layout: post
permalink: /2014/01/15/neatline-release-apalooza-neatline-2-2-0-neatscape-astrolabe/
enclosure:
  - |
    |
        
        
        
syndication_source:
  - 'Scholars&#039; Lab » neatline'
syndication_source_uri:
  - http://www.scholarslab.org
syndication_source_id:
  - http://www.scholarslab.org/tag/neatline/feed
"rss:comments":
  - 'http://www.scholarslab.org/announcements/neatline-2-2-0/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/announcements/neatline-2-2-0/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/announcements/neatline-2-2-0/
syndication_item_hash:
  - 5867cbd37a8aac9db4f61e31709e144a
categories:
  - Announcements
  - neatline
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=Neatline+release-apalooza%3A+Neatline+2.2.0%2C+Neatscape%2C+Astrolabe&rft.source=Scholars%26%23039%3B+Lab&rft.date=2014-01-15&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fannouncements%2Fneatline-2-2-0%2F&rft.language=English&rft.subject=Announcements&rft.aulast=McClure&rft.aufirst=David"></span> 
Today we&#8217;re excited to announce the release of Neatline 2.2.0! This is a big update that ships out a cluster of features and fixes that address a couple of rough spots identified by users over the course of the last couple months. 2.2.0 focuses on improvements in two areas &#8211; first, we&#8217;ve overhauled the workflows that connect Neatline records with Omeka items to make them more intuitive, flexible, and feature-rich, with the goal of making the overall integration between the two environments feel more seamless and low-friction. Second, we&#8217;ve added a system of interactive documentation to the editor that builds reference materials and tutorials directly into the interface, which should make it easier for new users to find their way around.

We&#8217;re also pushing out maintenance releases of the two extensions, NeatlineSimile and NeatlineWaypoints, which add compatibility for Neatline 2.2 and deal with a couple of minor bugs. As always, grab the code from the Omeka addons repository:

**[Neatline 2.2.0][1]** | **[NeatlineSimile 2.0.1][2]** | **[NeatlineWaypoints 2.0.2][3]**

What&#8217;s more, we&#8217;re also making release candidates available for two new Omeka themes designed to showcase Neatline exhibits: [Astrolabe][4] and [Neatscape][5]. Loyal readers may recall that a while back, we [ran a theme naming contest][6], and we&#8217;re finally making good on our word! These are just release candidates, but we wanted to get them out in the open for testing and feedback before cutting off stable releases. Give them a spin, and be sure to file a ticket on the respective issue trackers ([Astrolabe][7] and [Neatscape][8]) if you find quirks or need new features.

Some highlights in Neatline 2.2:

*   **Adds a new interface for linking Neatline records to Omeka items** that makes it possible to browse the entire collection of items, run full-text searches, and instantaneously preview the Omeka content (metadata, images, etc.) as it will appear in the public Neatline exhibit. 
    [<img src="http://dclure.org/wp-content/uploads/2014/01/item-binding.gif" alt="item-binding" width="312" height="771" class="alignnone size-full wp-image-3379" />][9]

*   **Frees up the &#8220;Title&#8221; and &#8220;Body&#8221; fields for modification on Neatline records linked to Omeka items**. Previously, these fields were automatically populated with the item content imported from Omeka, making it impossible to add custom information not contained in the Omeka metadata. Now, Neatline leaves these fields open for editing and displays them above the content synced in from Omeka, making it possible (though not required) to add exhibit-specific headings and text descriptions for imported items.
*   **Makes it possible to import raw data from the Dublin Core &#8220;Coverage&#8221; field**. When Omeka items are imported into Neatline exhibits, existing values in the Dublin Core &#8220;Coverage&#8221; field (either KML or WKT strings) are now automatically imported into Neatline and displayed on the map. Previously, this only worked if the coverage on the item was created with the Neatline Features plugin. With this functionality in place, it&#8217;s much easier to bulk-import existing spatial data sets &#8211; use the [CSV Import][10] plugin to populate a collection of items, and then push the new items to a Neatline exhibit.

*   **Adds interactive documentation to the editor** that builds reference materials for each individual control directly into the interface. Now, the heading for each input is followed by a little &#8220;**?**&#8221; button that, when clicked, overlays a document with information about what the control does, how to use it, and how it interacts with other functionality. The goal is to make the editor effectively self-documenting, so that it&#8217;s unnecessary to find separate documentation and toggle back and forth between different tabs as you work. 
    [<img src="http://dclure.org/wp-content/uploads/2014/01/interactive-docs.gif" alt="interactive-docs" width="1261" height="771" class="alignnone size-full wp-image-3381" />][11]

Last semester was a busy one for Neatline &#8211; we were supporting twelve classes here at UVa that are using Neatline for research assignments, and had the good fortune to collaborate with a number of folks at Harvard, Stanford, Northeastern, Duke, Indiana, and elsewhere who were using Neatline or gearing up for upcoming projects in the new year. We&#8217;ve also got a couple of exciting ideas brewing here in the lab for new, Neatline-powered projects &#8211; keep an eye on this space over the course of the next couple months.

As always, don&#8217;t hesitate to file bug reports on the [issue tracker][12], post questions to the [forums][13], or [contact us directly][14]. Happy new year!

 [1]: http://omeka.org/add-ons/plugins/neatline/
 [2]: http://omeka.org/add-ons/plugins/neatlinesimile/
 [3]: http://omeka.org/add-ons/plugins/neatlinewaypoints/
 [4]: http://omeka.org/add-ons/themes/astrolabe/
 [5]: http://omeka.org/add-ons/themes/neatscape/
 [6]: http://www.scholarslab.org/announcements/neatline-omeka-theme-name-winners/
 [7]: https://github.com/scholarslab/astrolabe/issues
 [8]: https://github.com/scholarslab/neatscape/issues
 [9]: http://dclure.org/wp-content/uploads/2014/01/item-binding.gif
 [10]: http://omeka.org/add-ons/plugins/csv-import/
 [11]: http://dclure.org/wp-content/uploads/2014/01/interactive-docs.gif
 [12]: https://github.com/scholarslab/Neatline/issues
 [13]: http://omeka.org/forums/forum/plugins
 [14]: mailto:neatline@collab.itc.virginia.edu
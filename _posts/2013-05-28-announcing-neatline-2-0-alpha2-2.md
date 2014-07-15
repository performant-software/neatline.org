---
title: Announcing Neatline 2.0-alpha2!
author: dm4fn
excerpt: '[Cross-posted with dclure.org] We&rsquo;re pleased to announce Neatline 2.0-alpha2, a second developer-preview version that gets us one step closer to a stable 2.0 release! For now, this is still just an testing release aimed at engineers and other folks who want to experiment with the new set of features (for more information, check out the&hellip;. <a href="http://www.scholarslab.org/geospatial-and-temporal/announcing-neatline-2-0-alpha2/">More.</a>'
layout: post
permalink: /2013/05/28/announcing-neatline-2-0-alpha2-2/
syndication_source:
  - 'Scholars&#039; Lab » neatline'
syndication_source_uri:
  - http://www.scholarslab.org
syndication_source_id:
  - http://www.scholarslab.org/tag/neatline/feed
"rss:comments":
  - 'http://www.scholarslab.org/geospatial-and-temporal/announcing-neatline-2-0-alpha2/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/geospatial-and-temporal/announcing-neatline-2-0-alpha2/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/geospatial-and-temporal/announcing-neatline-2-0-alpha2/
syndication_item_hash:
  - 364b6dc6e59d0a5f67519094efceda79
  - 158528a9c5c619d4db3d7701cbb8bdbb
  - de6cfb95c988eb436c3cd7a4ced25318
enclosure:
  - |
    |
        
        
        
categories:
  - Geospatial and Temporal
  - neatline
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=Announcing+Neatline+2.0-alpha2%21&rft.source=Scholars%26%23039%3B+Lab&rft.date=2013-05-28&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fgeospatial-and-temporal%2Fannouncing-neatline-2-0-alpha2%2F&rft.language=English&rft.subject=Geospatial+and+Temporal&rft.aulast=McClure&rft.aufirst=David"></span> 
*[Cross-posted with [dclure.org][1]]*

We&#8217;re pleased to announce Neatline 2.0-alpha2, a second developer-preview version that gets us one step closer to a stable 2.0 release! For now, this is still just an testing release aimed at engineers and other folks who want to experiment with the new set of features (for more information, check out the [announcement for the first testing release][2]). Grab the code here:

**[Neatline-2.0-alpha2][3] | [NeatlineWaypoints-2.0-alpha2][4] | [NeatlineSimile-2.0-alpha2][5]**

This revision fixes a couple of bugs and adds two new features that didn&#8217;t make it into the first preview release:

1.  **A user-privileges system**, which makes Neatline much easier to use in collaborative, multi-user settings like classrooms and workshops. In a lot of ways, this feature reflects an expanded focus for Neatline. During the first cycle of development last year, we were mainly focused on building a tool designed for individual scholars and students working on focused projects. In that setting &#8211; when just a handful of trusted collaborators are working on a project &#8211; it&#8217;s often not necessary to assign &#8220;ownership&#8221; to individual pieces of content to protect them from being changed or deleted by other users.</p> 
    Over the course of the last year, though, we&#8217;ve realized that there&#8217;s a lot of interest in using Neatline in a classroom setting, which introduces a new set of requirements. When 50 students are all building their own Neatline exhibits inside a single installation of Omeka, it would be easy for someone to accidentally edit or delete someone else&#8217;s work &#8211; there need to be guard rails to prevent users from modifying content that doesn&#8217;t belong to them.
    
    In Neatline 2.0-alpha2, we&#8217;ve added an ACL (access control list) that makes it possible to enforce a three-level user privileges system:
    
    *   **Admin** and **Super** users can do everything &#8211; they can create, edit, and delete all Neatline exhibits and records, regardless of who they were originally created by.
    
    *   **Contributor** users can add, edit, and delete their own exhibits, but can&#8217;t make changes to exhibits or records that they didn&#8217;t create.
    
    *   **Researcher** users are denied all Neatline-related privileges &#8211; they can&#8217;t create, edit, or delete any Neatline exhibits or records.
    
    This is a simple approach, but we think it addresses most of the basic patterns for classroom use that we&#8217;ve encountered here at UVa and elsewhere. If students are working on individual projects, each can be given a separate &#8220;Contributor&#8221; account, which allows them to create and update their own exhibits, but blocks them from changing anyone else&#8217;s work. If students are working together in groups, each group can be assigned an individual &#8220;Contributor&#8221; account, which allows group members to update each other&#8217;s work, but prevents them from making changes other groups&#8217; exhibits. </li> 
    *   **An exhibit-specific theming system** that makes it possible to create completely custom &#8220;sub-themes&#8221; for individual Neatline exhibits. Before, it was possible to customize the layout and styling of the Neatline exhibit views by editing the Omeka theme, which would change the appearance of *all* the exhibits on the site. In many cases, though, individual exhibits have specific requirements. Depending on the content, it might be useful for different exhibits to have different page headers, typography, or viewport layouts; and it&#8217;s also really useful to be able to load exhibit-specific JavaScript files, which can be used to define custom interactions for individual exhibits.</p> 
        In this release, every aspect of an exhibit&#8217;s public view can be completely customized by adding an &#8220;exhibit theme&#8221; that sits inside of the regular Omeka theme. For example, if I have an exhibit called &#8220;Testing Exhibit&#8221; with a URL slug of `testing-exhibit`, I can define a custom theme for the exhibit by adding a directory in the public theme at `neatline/exhibits/themes/testing-exhibit`. With the directory in place, Neatline will automatically load any combination of custom assets:
        
        *   If a `template.php` file is present in the directory, it will be used as the view template for the exhibit in place of the default `show.php` template that ships with Neatline.
        
        *   All `.js` and `.css` files in the directory will be loaded in the public view. This makes it possible to break additional styling and JavaScript functionality across multiple files, which makes it easier to break complex customizations into smaller units.
        
        This gives the theme developer full control over the appearance and behavior of each individual exhibit, making it possible to build a extremely diverse collection of Neatline projects inside a single installation of Omeka.</ol> 
    
    Check out the [change log][6] for more details. And let us know what you think!

 [1]: http://dclure.org/logs/announcing-neatline-2-0-alpha2/
 [2]: http://www.scholarslab.org/geospatial-and-temporal/announcing-neatline-2-0-alpha1/
 [3]: http://www.scholarslab.org/wp-content/uploads/2013/05/Neatline-2.0-alpha2.zip
 [4]: http://www.scholarslab.org/wp-content/uploads/2013/05/NeatlineWaypoints-2.0-alpha2.zip
 [5]: http://www.scholarslab.org/wp-content/uploads/2013/05/NeatlineSimile-2.0-alpha2.zip
 [6]: https://github.com/scholarslab/Neatline/blob/develop/CHANGELOG.md#v20-alpha2-commits
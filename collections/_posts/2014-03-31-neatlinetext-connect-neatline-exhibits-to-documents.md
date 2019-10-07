---
title: 'NeatlineText: Connect Neatline exhibits to documents'
author: dm4fn
excerpt: 'Download the plugin Today we&rsquo;re pleased to announce the first public release of NeatlineText, which makes it possible to create interactive, Neatline-enhanced editions of text documents &ndash; literary and historical texts, articles, book chapters, dissertations, blog posts, etc. &ndash; by connecting individual paragraphs, sentences, and words with objects in Neatline exhibits. Once the associations are&hellip;. <a href="http://www.scholarslab.org/announcements/neatline-text/">More.</a>'
layout: post
permalink: /2014/03/31/neatlinetext-connect-neatline-exhibits-to-documents/
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
  - 'http://www.scholarslab.org/announcements/neatline-text/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/announcements/neatline-text/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/announcements/neatline-text/
syndication_item_hash:
  - 981d3293b85008d9532ef97616b686e0
categories:
  - Announcements
  - neatline
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=NeatlineText%3A+Connect+Neatline+exhibits+to+documents&rft.source=Scholars%26%23039%3B+Lab&rft.date=2014-03-31&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fannouncements%2Fneatline-text%2F&rft.language=English&rft.subject=Announcements&rft.aulast=McClure&rft.aufirst=David"></span>  
## [Download the plugin][1]

[<img src="http://www.scholarslab.org/wp-content/uploads/2014/03/nltext-detail-1024x442.jpg" alt="nltext-detail" width="1024" height="442" class="aligncenter size-large wp-image-9950" />][1]

Today we&#8217;re pleased to announce the first public release of **[NeatlineText][1]**, which makes it possible to create interactive, Neatline-enhanced editions of text documents &#8211; literary and historical texts, articles, book chapters, dissertations, blog posts, etc. &#8211; by connecting individual paragraphs, sentences, and words with objects in Neatline exhibits. Once the associations are established, the plugin wires up two-way linkages in the user interface between the highlighted sections in the text and the imagery in the exhibit. Click on the text, and the exhibit focuses around the corresponding location or annotation. Or, click on the map, and the text scrolls to show the corresponding sections in the text.

We&#8217;ve been using some version of this code in internal projects here at the lab for almost two years, and it&#8217;s long overdue for a public release. The rationale for NeatlineText is pretty simple &#8211; again and again, we&#8217;ve found that Neatline projects often go hand-in-hand with some kind of regular text narrative that sets the stage, describes the goals of project, or lays out an expository thesis that would be hard to weave into the more visual, free-form world of the Neatline exhibit proper. This is awesome combination &#8211; tools like Neatline are really good at displaying spatial, visual, dimensional, diagrammatic information, but nothing beats plain old text when you need to develop a nuanced, closely-argued narrative or interpretation.

The difficulty, though, is that it&#8217;s hard to combine the two in a way that doesn&#8217;t favor one over the other. We&#8217;ve taken quite a few whacks at this problem over the course of the last few years. One option is to present the text narrative as a kind of &#8220;front page&#8221; of the project that links out to the interactive environment. But this tends to make the Neatline exhibit feel like an add-on, something grafted onto the project as an after-thought. And this can easily become a self-fulfilling prophecy &#8211; when you have the click back and forth between different web pages to read the text and explore the exhibit, you tend to write the text as a more or less standalone piece of writing, instead of weaving the narrative in with the conceptual landscape of the exhibit.

Another option is to chop the prose narrative up into little chunks and build it directly into the exhibit &#8211; like the numbered waypoints we used in the [the][2] [Hotchkiss][3] [projects][4] back in 2012, each waypoint containing a small portion of a longer interpretive essay. But this tends to err in the other direction, dissolving the text into the visual organization of the exhibit instead of presenting it as a first-class piece of content.

NeatlineText tries to solves the problem by just plunking the two next to each other and making it easy for the reader (and the writer!) to move back and forth between the two. For example, NeatlineText powers the interactions between the text and imagery in [these][5] [two][6] exhibits of NASA photograph from the 1960s:

[<img src="http://www.scholarslab.org/wp-content/uploads/2014/03/nltext-gemini-1024x619.jpg" alt="nltext-gemini" width="1024" height="619" class="aligncenter size-large wp-image-9941" />][7]

[<img src="http://www.scholarslab.org/wp-content/uploads/2014/03/nltext-saturn-v-1024x615.jpg" alt="nltext-saturn-v" width="1024" height="615" class="aligncenter size-large wp-image-9942" />][6]

(Yes, I know &#8211; I&#8217;m a space nerd.) NeatlineText is also great for creating interactive editions of primary texts. An earlier version of this code powers the [Mapping the Catalog of Ships][8] project by Jenny Strauss Clay, Courtney Evans, and Ben Jasnow (winner of the Fortier Prize prize at DH2013!), which connects the contingents in the Greek army mentioned in Book 2 of the Iliad with locations on the map:

[<img src="http://www.scholarslab.org/wp-content/uploads/2014/03/nltext-ships-1024x614.jpg" alt="nltext-ships" width="1024" height="614" class="aligncenter size-large wp-image-9944" />][8]

And NeatlineText was also used in this interactive edition of the [first draft of the Gettysburg Address][9]:

[<img src="http://www.scholarslab.org/wp-content/uploads/2014/03/nltext-gettysburg-1024x611.jpg" alt="nltext-gettysburg" width="1024" height="611" class="aligncenter size-large wp-image-9943" />][10]

Anyway, grab the code from the [Omeka add-ons repository][1] and check out the [documentation][11] for step-by-step instructions about how to get up and running. And, as always, be sure to [file a ticket][12] if you run into problems!

 [1]: http://omeka.org/add-ons/plugins/neatlinetext
 [2]: http://hotchkiss.neatline.org/neatline-exhibits/show/chancellorsville-may-2-1863-132/fullscreen
 [3]: http://hotchkiss.neatline.org/neatline-exhibits/show/battle-of-chancellorsville/fullscreen
 [4]: http://hotchkiss.neatline.org/neatline-exhibits/show/my-dear-little-nelly/fullscreen
 [5]: http://neatline.dclure.org/neatline/show/gemini-over-baja-california
 [6]: http://neatline.dclure.org/neatline/show/saturn-v-stage-2
 [7]: http://dclure.org/logs/project-gemini-over-baja-california/
 [8]: http://ships.lib.virginia.edu/neatline-editions/271
 [9]: http://neatline.dclure.org/neatline/show/gettysburg-address
 [10]: http://dclure.org/logs/nicolay-copy-gettysburg-address/
 [11]: https://github.com/scholarslab/nl-widget-Text#neatlinetext
 [12]: https://github.com/scholarslab/nl-widget-Text/issues
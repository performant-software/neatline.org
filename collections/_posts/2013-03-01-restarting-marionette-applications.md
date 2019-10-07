---
title: Restarting Marionette applications
author: dm4fn
excerpt: '[Cross-posted from dclure.org] Over the course of the last couple months, I&rsquo;ve been using Derick Bailey&rsquo;s superb Marionette framework for Backbone.js to build the new version of Neatline. Marionette sits somewhere in the hazy zone between a library and a framework &ndash; it&rsquo;s really a collection of architectural components for large front-end applications that can&hellip;. <a href="http://www.scholarslab.org/research-and-development/restarting-marionette-applications/">More.</a>'
layout: post
permalink: /2013/03/01/restarting-marionette-applications/
syndication_source:
  - 'Scholars&#039; Lab » neatline'
syndication_source_uri:
  - http://www.scholarslab.org
syndication_source_id:
  - http://www.scholarslab.org/tag/neatline/feed
"rss:comments":
  - 'http://www.scholarslab.org/research-and-development/restarting-marionette-applications/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/research-and-development/restarting-marionette-applications/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/research-and-development/restarting-marionette-applications/
syndication_item_hash:
  - ecc810fd0cbc8c3fa19f6064123690ed
  - 80b63eb76786740cc368f46e6187b7d4
  - 25f50f5febf420ed0d9405d43ea9d1d8
enclosure:
  - |
    |
        
        
        
categories:
  - backbone
  - Jasmine
  - javascript
  - marionette
  - neatline
  - Research and Development
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=Restarting+Marionette+applications&rft.source=Scholars%26%23039%3B+Lab&rft.date=2013-03-01&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fresearch-and-development%2Frestarting-marionette-applications%2F&rft.language=English&rft.subject=Research+and+Development&rft.aulast=McClure&rft.aufirst=David"></span> 
*[Cross-posted from [dclure.org][1]]*

Over the course of the last couple months, I&#8217;ve been using Derick Bailey&#8217;s superb [Marionette][2] framework for Backbone.js to build the new version of Neatline. Marionette sits somewhere in the hazy zone between a library and a framework &#8211; it&#8217;s really a collection of architectural components for large front-end applications that can be composed in lots of different ways. I use Marionette mainly for the core set of message-passing utilities, which make it easy to define interactions among different parts of big applications &#8211; pub-sub event channels, command execution, request-response patterns, etc. I&#8217;ve come to completely rely on these structures, and can&#8217;t really imagine writing non-trivial applications without them anymore.

The only big kink I&#8217;ve encountered is in the Jasmine suite. Since almost all of the integration-level test cases mutate the state of the application (trigger routes, open/close views, etc.), I needed to completely burn down the app and re-start it from scratch at the beginning of each test to ensure a clean slate. The top-level Marionette `Application` has a `start` method that walks down the tree of modules and runs the initializers. As it exists now, though, `start` can only be called once during the lifecycle of the application, and does nothing if it&#8217;s called again later on.

I was getting around this by defining independently-callable `init` methods for all of my modules and wiring them up to the regular Marionette start-up system:



But then manually calling all of the init methods in my Jasmine start-up routine to force-restart the application:



This is icky &#8211; I have to exactly recreate a specific start-up order that&#8217;s automatically enforced in the application itself by `before:` and `after:` initialization events. And it introduces lots of opportunities for false-negatives &#8211; if you add a module, and forget to explicitly start it in the test suite, everything falls apart. 

Really, I wanted to just re-call `Neatline.start()` before every test. I realized tonight, though, that the application object can be tricked into restarting itself by (a) stopping all of the modules and (b) resetting the top-level `Callbacks` on the application:



Much cleaner. Assuming all state-bearing components are instantiated in the initializers, this has the desired effect of completely rebooting the application.

I&#8217;d imagine this is a pretty common issue &#8211; is there any philosophical reason for the prohibition against re-calling `Application.start()` more than once?

 [1]: http://dclure.org/logs/restarting-marionette-applications/
 [2]: https://github.com/marionettejs/backbone.marionette
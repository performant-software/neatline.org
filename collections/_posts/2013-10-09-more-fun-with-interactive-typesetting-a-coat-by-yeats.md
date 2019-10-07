---
title: 'More fun with interactive typesetting: “A Coat,” by Yeats'
author: dm4fn
excerpt: '[Cross-posted from dclure.org] Click here to view the exhibit. After spending the weekend tinkering around with an interactive typesetting of a couplet from Macbeth that tried to model reading as a process of zooming downward towards the end of the phrase, I became curious about experimenting with the opposite analogy &ndash; reading as an upward&hellip;. <a href="http://www.scholarslab.org/experimental-humanities/more-fun-with-interactive-typesetting-a-coat-by-yeats/">More.</a>'
layout: post
permalink: /2013/10/09/more-fun-with-interactive-typesetting-a-coat-by-yeats/
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
  - 'http://www.scholarslab.org/experimental-humanities/more-fun-with-interactive-typesetting-a-coat-by-yeats/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/experimental-humanities/more-fun-with-interactive-typesetting-a-coat-by-yeats/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/experimental-humanities/more-fun-with-interactive-typesetting-a-coat-by-yeats/
syndication_item_hash:
  - 3d0a5badaae25559ddd00c4956e587d0
  - 7062e5ba8c9c669f42e598877dcd4ed0
categories:
  - Experimental Humanities
  - neatline
  - yeats
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=More+fun+with+interactive+typesetting%3A+%22A+Coat%2C%22+by+Yeats&rft.source=Scholars%26%23039%3B+Lab&rft.date=2013-10-09&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fexperimental-humanities%2Fmore-fun-with-interactive-typesetting-a-coat-by-yeats%2F&rft.language=English&rft.subject=Experimental+Humanities&rft.aulast=McClure&rft.aufirst=David"></span> 
*[Cross-posted from [dclure.org][1]]*

## [Click here to view the exhibit][2].



After spending the weekend [tinkering around with an interactive typesetting of a couplet from Macbeth][3] that tried to model reading as a process of zooming *downward* towards the end of the phrase, I became curious about experimenting with the opposite analogy &#8211; reading as an *upward* movement, an climb from the bottom (the beginning) to the top (the end), with each word circumscribing everything that comes before it. Really, this is just the flip side of the same coin. Meaning certainly flows &#8220;downhill&#8221; in a phrase &#8211; each word is informed by the previous word. But it also flows back &#8220;uphill&#8221; &#8211; each word casts new meaning onto what comes before it. What would it would feel like to visualize that?

This time I decided to work with &#8220;A Coat,&#8221; Yeats&#8217; wonderful little ode to simplicity (he renounces what he thinks to be the stylistic affectation of his work from the 1890’s, and announces an intention to write &#8220;naked[ly]&#8220;). Originally, I planned to exactly invert the layout of the Macbeth couplet &#8211; start with the &#8220;I&#8221; at the bottom of the stack, and work upwards towards the end with &#8220;naked,&#8221; which, in the final frame, would geometrically contain each of the preceding words. I started to do this, but quickly ran into an interesting computational obstacle, which actually cropped up in the Shakespeare example as well.

Trip Kirkpatrick noticed the problem:

<blockquote class="twitter-tweet">
  <p>
    <a href="https://twitter.com/clured">@clured</a> Are jaggies on deepest zoom artifacts results of zoomed pixels or aesthetic decisions? Both?
  </p>
  
  <p>
    &mdash; Trip Kirkpatrick (@triplingual) <a href="https://twitter.com/triplingual/statuses/387254660563992576">October 7, 2013</a>
  </p>
</blockquote>



Indeed, the last two words &#8211; &#8220;way&#8221; and &#8220;comes&#8221; &#8211; are pixelated and malformed:

[<img src="http://dclure.org/wp-content/uploads/2013/10/way-300x151.jpg" alt="way" width="300" height="151" class="size-medium wp-image-3114" />][4]

[<img src="http://dclure.org/wp-content/uploads/2013/10/comes-300x93.jpg" alt="comes" width="300" height="93" class="size-medium wp-image-3113" />][5]

This wasn&#8217;t on purpose &#8211; I couldn&#8217;t figure out why it was happening when I was working on the exhibit, but decided against trying to fix it, half out of laziness and half because the visual effect had some satisfying affinities with the content of the line, especially when paired with the &#8220;descending&#8221; motif &#8211; a plunge down to hell, where order disintegrates, smooth lines are forbidden, etc. Anyway &#8211; after thinking it over, I&#8217;m pretty sure I know what&#8217;s going on, although I&#8217;m not certain. At the extremely deep zoom levels (far beyond anything you&#8217;d ever need for a regular map), I think that OpenLayers is actually losing the floating point precision that it needs to accurately plot the SVG paths for the letters &#8211; the computer is running out of decimal places, essentially.

I squeaked by with the Macbeth couplet, but this turned out to be a showstopper for the Yeats, since I was effectively trying to plot geometry about four and a half times deeper &#8211; 45 words versus 11. At that depth, the text becomes completely illegible, so I had to find a way to squeeze more content into fewer zoom levels. In the end, I managed to fit it all in by positioning each line into a geometric “notch” formed by the ascenders of two letters on the following line, which more or less preserves the philosophical rationale of the exhibit (each bit of text &#8220;envelops&#8221; the previous, if somewhat less completely than before) while limiting the zooming to just ten magnification contexts, one for each line.

[<img src="http://dclure.org/wp-content/uploads/2013/10/heel-300x114.jpg" alt="heel" width="300" height="114" class="size-medium wp-image-3131" />][6]

To scan the poem, just zoom out by clicking on the &#8220;minus&#8221; button (or scrolling the mouse wheel or pinching the screen, if applicable), or click on the lines in the reference text at the top left to auto-focus on a particular part of the poem.

 [1]: http://dclure.org/essays/more-fun-with-interactive-typesetting-a-coat-by-yeats/
 [2]: http://neatline.dclure.org/neatline/show/a-coat
 [3]: http://dclure.org/essays/experimental-typesetting-with-neatline-and-shakespeare/
 [4]: http://dclure.org/wp-content/uploads/2013/10/way.jpg
 [5]: http://dclure.org/wp-content/uploads/2013/10/comes.jpg
 [6]: http://dclure.org/wp-content/uploads/2013/10/heel.jpg
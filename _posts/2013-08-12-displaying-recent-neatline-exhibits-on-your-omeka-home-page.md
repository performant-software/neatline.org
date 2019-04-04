---
title: Displaying Recent Neatline Exhibits on your Omeka Home Page
author: Jeremy Boggs
excerpt: 'The charismatic Alex Gil submitted a feature request to Neatline asking to be able to browse Neatline exhibits on your Omeka home page. Turns out you can already specify which page you want as your home page in Omeka 2.0, so that helped with Alex&rsquo;s original query. But as we discussed the issue, Alex also&hellip;. <a href="http://www.scholarslab.org/research-and-development/displaying-recent-neatline-exhibits-on-your-omeka-home-page/">More.</a>'
layout: post
permalink: /2013/08/12/displaying-recent-neatline-exhibits-on-your-omeka-home-page/
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
  - 'http://www.scholarslab.org/research-and-development/displaying-recent-neatline-exhibits-on-your-omeka-home-page/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/research-and-development/displaying-recent-neatline-exhibits-on-your-omeka-home-page/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/research-and-development/displaying-recent-neatline-exhibits-on-your-omeka-home-page/
syndication_item_hash:
  - 84cfb732c65c15118e8e75de7eda5029
  - b87de2e6861641bb8e2777a2f9377b64
categories:
  - neatline
  - omeka
  - php
  - Research and Development
  - themes
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=Displaying+Recent+Neatline+Exhibits+on+your+Omeka+Home+Page&rft.source=Scholars%26%23039%3B+Lab&rft.date=2013-08-12&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fresearch-and-development%2Fdisplaying-recent-neatline-exhibits-on-your-omeka-home-page%2F&rft.language=English&rft.subject=Research+and+Development&rft.aulast=Boggs&rft.aufirst=Jeremy"></span> 
The charismatic [Alex Gil][1] submitted a feature request to Neatline asking to be able to browse [Neatline exhibits on your Omeka home page][2]. Turns out you can already [specify which page you want as your home page in Omeka 2.0][3], so that helped with Alex&#8217;s original query. But as we discussed the issue, Alex also wondered about putting a list of recent Neatline exhibits on the home page, much the same way Omeka already does with recent items. While we&#8217;re not sure yet about putting this kind of thing in the plugin itself, I mentioned that it&#8217;s fairly easy to do in your own them using one of Omeka&#8217;s hooks, and promised him a blog post explaining more. Here&#8217;s me making good on that promise.

In case you didn&#8217;t know, Omeka has plenty of ways for developers to add new content to an Omeka site or filter existing content using hooks and filters, respectively. To use them, you first need to write a function that adds or changes content to your preference, then you pass that function to the relevant hook or filter in Omeka. Some dummy code to illustrate:

<pre class="brush: php; title: ; notranslate">&lt;?php

function my_custom_function() {
  echo 'Hello world!';
}

add_plugin_hook('hook_name', 'my_custom_function');

</pre>

You could put this kind of code anywhere that Omeka could run it, particularly a new plugin or your activated theme&#8217;s `custom.php` file. (An Omeka theme&#8217;s `custom.php` file is a great place to put some custom code for your Omeka site, without having to go to the trouble of creating and activating a plugin.)

In our case, we want to append some new content to the home page of an Omeka site, so we&#8217;ll need to find a hook to let us do that. Fortunately, we have one available—`public_home`—so let&#8217;s use that to display some recent Neatline exhibits.

(Keep in mind that the following code should work in Omeka 2.0 and Neatline 2.0; you can take a similar approach for earlier versions of each, but some of the functions would be different.)

First, we&#8217;ll need to create a `custom.php` file in your current active theme, if one doesn&#8217;t already exist. (If it does exist, we&#8217;ll use that one.) Make sure the file is in the root of your theme: `omeka/themes/your-theme/custom.php`.

Next we&#8217;ll need to write a function that gets a certain number of Neatline exhibits and lists them out, and put that in our `custom.php` file. We&#8217;ll name our function `display_recent_neatline_exhibits`, and put all our goodies in there. Let&#8217;s create the function:

<pre class="brush: php; title: ; notranslate">&lt;?php

function display_recent_neatline_exhibits() {

}

</pre>

After we&#8217;ve created the function, we&#8217;ll go ahead and pass that function to the `public_home` hook:

<pre class="brush: php; title: ; notranslate">&lt;?php

function display_recent_neatline_exhibits() {

}

add_plugin_hook('public_home', 'display_recent_neatline_exhibits');
</pre>

We still shouldn&#8217;t see any changes on the home page, since our function isn&#8217;t actually doing anything. But you shouldn&#8217;t get any errors on the page either. If you do, make sure you have every curly brace and semicolon and all the other characters right; PHP is quite dramatic about syntax errors.

Now lets add some stuff to our function to get some recent Neatline exhibits. First, let&#8217;s define a variable `$html` and set that equal to an empty string. In the end, we&#8217;ll echo the value of `$html`, so we want it equal to at least something, in case you actually don&#8217;t have any Neatline exhibits to display.

<pre class="brush: php; title: ; notranslate">&lt;?php

function display_recent_neatline_exhibits() {
    $html = '';

    echo $html;
}

add_plugin_hook('public_home', 'display_recent_neatline_exhibits');
</pre>

Next we&#8217;ll create a variable, `$neatlineExhibits`, and assign it to the results of a query using Omeka&#8217;s `get_records` function. The [`get_records` function][4] takes three arguments: the type of record, an array of query parameters, and number to limit results. We&#8217;ll query for &#8216;NeatlineExhibit&#8217; record type, make sure that the `recent` parameter is `true`, and limit our results to five:

<pre class="brush: php; title: ; notranslate">&lt;?php

function display_recent_neatline_exhibits() {
    $html = '';

    // Get our recent Neatline exhibits, limited to five.
    $neatlineExhibits = get_records('NeatlineExhibit', array('recent' =&gt; true), 5);

    echo $html;
}

add_plugin_hook('public_home', 'display_recent_neatline_exhibits');
</pre>

Now we&#8217;ll set the results in `$neatlineExhibits` for a record loop, and check to see if in fact we have exhibits to display in a PHP `if` statement:

<pre class="brush: php; title: ; notranslate">&lt;?php

function display_recent_neatline_exhibits() {
    $html = '';

    // Get our recent Neatline exhibits, limited to five.
    $neatlineExhibits = get_records('NeatlineExhibit', array('recent' =&gt; true), 5);

    // Set them for the loop.
    set_loop_records('NeatlineExhibit', $neatlineExhibits);
 
    // If we have any to loop, we'll append to $html.
    if (has_loop_records('NeatlineExhibit')) {

    }

    echo $html;
}

add_plugin_hook('public_home', 'display_recent_neatline_exhibits');
</pre>

Inside our `if` statement, we&#8217;ll update the value of `$html` so that, instead of echoing an empty string, it echos some HTML that includes links to each of our recent Neatline exhibits. Remember that this will only get printed if we actually have Neatline exhibits in the database, otherwise we&#8217;ll just return an empty string.

<pre class="brush: php; title: ; notranslate">&lt;?php

function display_recent_neatline_exhibits() {
    $html = '';

    // Get our recent Neatline exhibits, limited to five.
    $neatlineExhibits = get_records('NeatlineExhibit', array('recent' =&gt; true), 5);

    // Set them for the loop.
    set_loop_records('NeatlineExhibit', $neatlineExhibits);
 
    // If we have any to loop, we'll append to $html.
    if (has_loop_records('NeatlineExhibit')) {
        $html .= '&lt;ul&gt;';
        
        foreach (loop('NeatlineExhibit') as $exhibit) {
            $html .= '&lt;li&gt;'
                   . nl_getExhibitLink(
                         $exhibit,
                         'show',
                         metadata($exhibit, 'title'),
                         array('class' =&gt; 'neatline')
                     )
                   . '&lt;/li&gt;';
        }

        $html .= '&lt;/ul&gt;';
    }

    echo $html;
}

add_plugin_hook('public_home', 'display_recent_neatline_exhibits');
</pre>

As you can see, we append an opening unordered list tag, `<ul>` to `$html`. (Using `.=` in PHP lets us append additional strings onto an existing variable.) Then, we use Omeka&#8217;s `loop` function to loop through our set of Neatline exhibits. Inside that loop, we once again adding something to the value of `$html`: A list item wrapping a link to a the current Neatline exhibit in the loop. To help us make that link, we&#8217;ll use a function provided by the Neatline plugin: `nl_getExhibitLink`. We&#8217;re passing values for four arguments: The exhibit object (defined in `$exhibit` in the foreach loop); the `action` or route you want the link to take; the text of the link (here we&#8217;ve used Omeka&#8217;s `metadata` function to give us the title of the exhibit); and an array of attributes for the link (we&#8217;ve added a `class` attribute equal to &#8216;neatline&#8217;). Then we end with a closing list item tag.

And that should do it. You can see a version more or less the same as what I demonstrate here in a [public gist][5] I published earlier in the week. If you&#8217;d like to display a recent list of Neatline exhibits on your Omeka home page, just grab this code, and put it in your theme&#8217;s `custom.php` template.

 [1]: http://www.elotroalex.com/
 [2]: https://github.com/scholarslab/Neatline/issues/211
 [3]: http://omeka.org/codex/Managing_Navigation_2.0#Choose_a_Homepage
 [4]: http://omeka.readthedocs.org/en/latest/Reference/libraries/globals/get_records.html
 [5]: https://gist.github.com/clioweb/6178723
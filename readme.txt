=== Categories by Tag Table ===
Contributors: haroldstreet
Donate link: http://www.haroldstreet.org.uk/thanks/
Tags: html, table, categories, category, tags, tag, pivot, embed, list, navigation, menu, post, page, plugin, free
Requires at least: 2.0
Tested up to: 6.3

'Categories by Tag Table' displays all your Categories as rows and Tags as columns in a html table.

== Description ==

**'Categories by Tag Table'** allows you to display all your Categories as rows and Tags as columns in a html pivot table.
Once activated it will replace the text '**[CATS_BY_TAGS_TABLE]**' in any post or page with a table.
Each cell displays the number of published posts that are in both the category and have the tag, and a URL link to those posts.
It might be a useful way to list your content for navigation or embed as a menu.

The options menu allows you to:
* specify whether Categories are rows with tags as columns in the table or vice versa;
* specify the title text displayed in the top left cell;
* specify the url to your own CSS stylesheet to customise the styling to match your site;
* specify what to show in any empty cells;
* specify any charicters to remove from your Tag & Category names;

== Installation ==

1. Upload `cat-by-tags-table.php` to the `/wp-content/plugins/` directory
1. Activate the plugin through the 'Plugins' menu in WordPress
1. Configure through the 'Options' menu under Settings / Categories by Tag
1. Finally include the text '**[CATS_BY_TAGS_TABLE]**' in any post or page content 
1. alternatively you may place the following php code in your `page.php` file...
`<?php if(function_exists("display_cats_by_tag")){echo display_cats_by_tag();} ?>`

== Screenshots ==

1. The Options menu in Wordpress
1. An example 'Categories by Tag Table' generated in a post on my blog

== Frequently Asked Questions ==

= Can I customise the css styles of the table =
You can specify the style most of the table elements through linking to an external stylesheet of your own and styling the elements within the `<div id="catbytag">`.

The best way to do this is to copy the default stylesheet `default-css-settings.css` (downloaded with the plugin), edit it as you see fit and then save this new file somewhere else on your website. 
Finally provide the URL to your new stylesheet in the options. 

= The Table Header looks really weird in my old browser =
Modern browsers should render the header as text rotated rather than stacked vertically, this usually looks much better.

However if you have problems in Internet Explorer, then its probably this "nifty rotate text" css rule. 
To fix this edit the stylesheet (either the default one called `default-css-settings.css` via the plugin editor, or your own external one if you have used the option above) and completely delete the three lines marked that look like this...
`	max-height:7em !important;
	writing-mode:tb-rl !important;
	filter:flipv fliph !important;` 
Then replace them with...
`	max-width:0.5em;
	word-wrap: break-word;
	font-family:'Lucida Console',Monotype;
	vertical-align:bottom;`

= Can I change the sort order of how the Cats and Tags are displayed =
You need to edit the following lines in the plugin file `cat-by-tags-table.php`
(You can do this from within Wordpress using the plugin editor at `#blogurl#/wp-admin/plugin-editor.php`)
so from line 111 in the file the plugin default code is....
`	$cat_args=array(
	 'orderby' => 'name',
	 'order' => 'ASC',
	 'taxonomy' => 'category'
	 );

	$tag_args=array(
	 'orderby' => 'name',
	 'order' => 'ASC',
	 'taxonomy' => 'post_tag'
	 );`
you need to replace the `'ASC'` with `'DESC'` in both places, save the changes and it should work .

= Can I display the count of all posts (drafts + private) not just those that are published? =
Yes just delete the following line...
`	$countsql.="JOIN $wpdb->posts AS E ON E.ID = A.object_id AND E.post_status = 'publish' ";`
from the plugin file `cat-by-tags-table.php`

= Can I use images instead? =
Have a look at version 1002.14 its adapated specially to use images


== Changelog ==

= 2.14 =
Bug fix for database errors with WP 4.1.2

= 2.13 =
Remove empty rows

= 2.12 =
CSS3 solution to rotating Header text

= 2.11 =
2nd Bug Fix for WP 4.1.1

= 2.10 =
Bug Fix for WP 4.1.1

= 2.09 =
No longer counts Draft or Private Posts only Public ones.

= 2.08 =
Bug Fix for renumbered categories in WP 4.0

= 2.07 =
Update to ensure compatability with WP 3.5.0

= 2.06 =
Further improvements to the MySQL Querys for even better efficiency

= 2.05 =
Improvements to the MySQL Querys used for better efficiency

= 2.04 =
Minor revisions and improvements to the new stylesheet options

= 2.03 =
Option to link to an external stylesheet of your choice, instead of just the style element for the td cells

= 2.02 =
a dud upload - no idea what happened here!

= 2.01 =
A major revision of the code and some new options

= 1.04 =
Some minor spelling corrections

= 1.03 =
New options added

= 1.02 =
Tidy up a few minor bits and bobs

= 1.01 =
First stable release

= 1000.03 =
A custom version to display images 


== Upgrade Notice ==

= 2.14 =
Bug fix for database errors with WP 4.1.2

= 2.13 =
Remove empty rows

= 2.12 =
CSS3 solution to rotating Header text

= 2.11 =
2nd Bug Fix for WP 4.1.1

= 2.10 =
Bug Fix for WP 4.1.1

= 2.09 =
No longer counts Draft, Private or Password Protected Posts only Public ones.

= 2.08 =
Bug Fix for renumbered categories in WP 4.0

= 2.07 =
Update to ensure compatability with WP 3.5.0

= 2.06 =
Further improvements to the MySQL Querys for even better efficiency

= 2.05 =
Improvements to the MySQL Querys used for better efficiency

= 2.04 =
Improved option to link to an external stylesheet of your choice

= 2.03 =
Option to link to an external stylesheet of your choice, instead of just styling the element for the td cells

= 2.01 =
A major revision of the code and some new options

= 1.04 =
Some minor spelling corrections

= 1.03 =
Upgrade to customise contents of an empty cell

= 1.02 =
I wouldn't bother updating for this

= 1.01 =
First stable release


== License ==

Copyright 2011  Phil Newby  email: *phil (at) haroldstreet (dot) org (dot) uk* 

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
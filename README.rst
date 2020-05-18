+---+------------------------------------------------------------------------------------------------------------------+
| ❗ | This theme is for legacy OKFN wordpress sites. For new sites, please use https://github.com/okfn/wordpress-theme |
+---+------------------------------------------------------------------------------------------------------------------+


=================
OKFN Legacy Theme
=================

This is a theme based on the BuddyPress bp-default theme.
http://codex.buddypress.org/theme-development/building-a-buddypress-child-theme/


We override::

  header.php
  footer.php
  single.php
  style.css

And additionally provide function hooks in::

  functions.php
  shortcodes.php

...and that's it! Wordpress' output is modified via callbacks in functions.php. We structure the page in header/footer but aim to use the parent theme's templates in all other cases. Wordpress always provides a more robust override mechanism.


Templates
---------

**Magazine**

To create a magazine frontpage for your blog, create a page and choose 'Magazine' as its Template (on the right hand side).

Magazine mode will display:

* The latest blogpost with the category "Featured" at the top.
* The latest four blogposts which aren't that one beneath it.

The magazine template will display the 'Featured Image' from each blog post.

There is a simple algorithm to choose which category is displayed on the ribbon. The priority order of categories can be viewed and overwritten in the 'Blog' section of the theme options.

To use YARPP to display Related Posts as magazine entries on the post view page, open up the YARPP widget settings.

* Disable "Automatically display related posts"
* Select "Display using a custom template file" (yarpp-template-magazine.php)


**Home**

The Home template adds Magazine style blogposts to the bottom of the page. By default, only posts in a category named "Featured" will be displayed (this category can be changed in the 'Blog' section of the theme options). Images are handled in the same manner as described above.


**Presentation**

Display content in a series of slides. Example here: http://staging.okfn.org/slides/


Theme Options
-------------

The theme can be customised in a variety of ways via the Theme Options. These settings can be found in WordPress admin under Appearance >OKF Theme Options.


Supported Shortcode
-------------------

**Carousel**

To add a carousel to your page can be as simple as::

  [carousel]
  [slide img="http://slide1.jpg" class="active"]
  [slide img="http://slide2.jpg"]
  [/carousel]

Please note that one of the slides must have ``class="active"`` applied to it, this will be the first slide that is displayed.

Some predefined classes can be applied to the carousel to alter the styling::

  text-right photo-stack

Other supported attributes are ``heading`` and ``caption``. For example, to add a caption to a slide you would enter it as follows:::

  [carousel]
  [slide img="http://slide1.jpg" class="active"]
  [slide img="http://slide2.jpg" caption="My caption for slide two"]
  [/carousel]


**Static Banner**

If you only want a single banner image, use the below::

  [banner bg="http://domain.com/bg-image.jpg"]
  Banner text here.
  [/banner]


**Pseudo Sidebar**

If you are using the 'One column, no sidebar' template to hide the default sidebar, you can mimic the default layout like so:::

  [pseudocontent] My main content [/pseudocontent]
  [pseudosidebar] My sidebar content [/pseudosidebar]

**Image Caption**

Wrap an image and its caption in a border

::

  [caption width="450" caption="My caption"]
  <img src="http://image.jpg" alt="" width="450" />
  [/caption]


**Hide Page Title**

Use to hide the page title

::

  [notitle]


**Full Width**

Force content div to be 100% wide

::

  [fullwidth]


**BS Columns**

Divide single column. Span is a number of the 12 Bootstrap columns

::

  [row]
  [column span="6"]
  Left Column Content
  [/column]
  [column span="6"]
  Right Column Content
  [/column]
  [/row]


**Clear**

Clear floats

::

  [clear]


**Accordions**

Use ``class="in"`` to have the accordion open by default

::

  [accordion heading="Heading One" class="in"] content [/accordion]
  [accordion heading="Heading Two"] content [/accordion]


**RSS Ticker**

Show scrolling previews from an RSS feed::

  [rss feed="http://planet.okfn.org/feed" type="ticker"]


**Image List**

List of images with text beside

::

  [il]
  [ili image="http://assets.okfn.org/web/images/blog-placeholder.png" title="Title One" description="Description One"]
  [ili image="http://assets.okfn.org/web/images/blog-placeholder.png" title="Title Two" description="Description Two"]
  [ili image="http://assets.okfn.org/web/images/blog-placeholder.png" title="Title Three" description="Description Three"]
  [/il]

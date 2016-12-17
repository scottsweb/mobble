![mobble](http://cloud.scott.ee/images/mobble.png)

# mobble

* Status: ✔ Active
* Contributors: [@scottsweb](http://twitter.com/scottsweb)
* Description: Helper plugin that provides conditional functions for detecting a variety of mobile devices & tablets.
* Author: [Scott Evans](http://scott.ee)
* Author URI: [http://scott.ee](http://scott.ee)
* License: GNU General Public License v2.0
* License URI: [http://www.gnu.org/licenses/gpl-2.0.html](http://www.gnu.org/licenses/gpl-2.0.html)

## About

mobble provides mobile related conditional functions for your site. e.g. `is_iphone()`, `is_mobile()` and `is_tablet()`.

CSS media queries are great for creating responsive web designs but they do not always provide enough control. There are times when not all of the content, JavaScript or CSS on a page is relevant for a particular device. With the mobble functions you can make these kind of tweaks to your theme.

mobble can also add device information to the body class of your theme allowing you to easily target your CSS for different gadgets.

## Installation

To install this plugin:

* Upload the `mobble` folder to the `/wp-content/plugins/` directory
* Activate the plugin through the 'Plugins' menu in WordPress
* You can now use `<?php is_mobile(); is_tablet(); // etc ?>` functions in your themes/templates
* If you want you can also disable the device specific body classes in the WordPress Admin->Settings->mobble setting section

Visit [WordPress.org for a comprehensive guide](http://codex.wordpress.org/Managing_Plugins#Manual_Plugin_Installation) on in how to install WordPress plugins.

## Hooks & Filters

...

## Frequently Asked Questions

###What functions are available?

The most useful ones are:

```
<?php
is_handheld(); // any handheld device (phone, tablet, Nintendo)
is_mobile(); // any type of mobile phone (iPhone, Android, etc)
is_tablet(); // any tablet device
is_ios(); // any Apple device (iPhone, iPad, iPod)
?>
```

You can also use:

```
<?php
is_iphone();
is_ipad();
is_ipod();
is_android();
is_blackberry();
is_opera_mobile();
is_symbian();
is_kindle();
is_windows_mobile();
is_motorola();
is_samsung();
is_samsung_tablet();
is_sony_ericsson();
is_nintendo();
?>
```

Inspecting `Mobile_Detect.php` will also reveal some other useful tools.

###Do you have any examples?

Yup. This first example disables the sidebar for mobile/phone devices:

```
<?php
if (!is_mobile()) {
	get_sidebar();
}
?>
```

This second example loads a specific stylesheet for Apple devices (iPhone, iPod and iPad):

```
<?php
if (is_ios()) {
	wp_enqueue_style('ios', get_template_directory_uri() . '/ios.css');
}
?>
```

###Caching
Please note that in certain setups caching will cause undesired behaviour. If your cache is set too aggressively PHP will be skipped and the device detection will not work.

## Changelog

####1.6
* Mobile Detect 2.8.24
* Add edge body class (props Luca Speranza)
* Add filters to functions (props Matthew Keasling)

####1.5
* Add German translation (props @rpkoller)
* Minor PHP improvements
* Mobile Detect 2.8.17

####1.4
* Run through PHP tidy
* Mobile detect update to 2.8.13

####1.3
* Update mobile detect library to 2.7.6
* Small CSS change for 3.8

####1.2.1
* Small bug fix on is_mobile()
* Moved screenshots out of trunk

####1.2
* Now uses mobile-detect (http://mobiledetect.net/) which provides more accurate and varied detection
* Mobiles can now be graded (A,B,C) using the mobile-detect API (see mobile-detect.php) or mobiledetect.net
* is_palm, is_lg, is_nokia will be removed soon - check depricated notices
* New check for is_kindle - feedback on this one appreciated as I cannot test it

####1.1
* Correction to the PHP.
* New body class of .desktop for anything not handheld
* Tested on 3.2+

####1.0
* Initial release.

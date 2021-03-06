=== Plugin Name ===
Contributors: gorpoghosyan589
Tags: optimize, wp-rocket, async css
Requires at least: 4.5
Tested up to: 4.9.2
Stable tag: trunk
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

WordPress plugin to combine all inline, external, and remote CSS and load async. Depends on WP-Rocket

This is NOT an official addon to WP-Rocket!

== Description ==

This plugin will combine all inline and external CSS in the order found on the page and save it to WP-Rocket's cache folder as a new file. Files with media attributes are wrapped in `@media` selectors during processing. Async is powered by [https://github.com/filamentgroup/loadCSS](https://github.com/filamentgroup/loadCSS).

If you need dedicated/professional assistance with this plugin or just want an expert to get your site to run the fastest it can be, you may hire me at [Freelacner.com](https://www.freelancer.com/u/gorpoghosyan)

Filters `rocket_async_css_process_style` and `rocket_async_css_process_file` can be used to selectively exclude any inline CSS or external CSS from minify and async loading.

Examples are:

~~~
function exclude_css($skip, $css){
    if ( false !== strpos( $css, 'something' ) ) {
			return false;
		}

	return $skip;
}
add_filter('rocket_async_css_process_style','exclude_css', 10, 2);
~~~

and

~~~
function exclude_file($skip, $url){
    if ( 'some url' == $url ) {
			return false;
	}

	return $skip;
}
add_filter('rocket_async_css_process_style','exclude_file', 10, 2);
~~~

== Installation ==

This section describes how to install the plugin and get it working.

1. Upload the plugin files to the `/wp-content/plugins/rocket-async-css` directory, or install the plugin through the WordPress plugins screen directly.
2. Activate the plugin through the 'Plugins' screen in WordPress
4. View HTML source, and test it out!


* Initial version
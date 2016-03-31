=== Advanced Custom Fields: Link Picker Field ===

Contributors: BIOSTALL, caalami
Tags: acf, advanced custom fields, link picker, link chooser, acf link picker
Requires at least: 3.5
Tested up to: 4.5
Stable tag: trunk
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Adds an Advanced Custom Field field that allows the selection of a link utilising the WordPress link picker modal dialog

== Description ==

This add on for the already established Advanced Custom Fields plugin adds a new field type called 'Link Picker' which allows the user to enter a URL, or select from the existing pages. It is a thin wrapper around the link selector included with the WYSIWYG field editor.

This plugin is forked from the plugin of the same name hosted at https://github.com/BIOSTALL/ACF-Link-Picker-Field. This version is hosted at https://github.com/ahebrank/ACF-Link-Picker-Field and issues and PRs should be submitted there.

Note: Advanced Custom Fields must be installed for this add-on to work.

== Compatibility ==

This ACF field type is compatible with:

*	ACF 5
*	ACF 4

== Installation ==

1. Copy the `acf-link_picker` folder into your `wp-content/plugins` folder
2. Activate the 'Advanced Custom Fields: Link Picker' plugin via the plugins admin page
3. Create a new field via ACF and select the Link Picker type

== Usage ==

When outputting the link selection on the front end, you will have three object elements available:

*	url - The URL of the page
*	title - The title of the link, if entered
*	target - Will be either a blank string or '_blank', depending on whether the user has ticked the box for the link to open in a new window/tab.
* postid - Not available as part of wp_link, this is an ajax hack to attempt to look up the post ID of a selected link. This will return 0 if the post ID was not found.

Code example:

`$mylink = get_field('mylink');`
`var_dump($mylink);`

Outputs:

`array(3) {
  ["url"]=>
  string(31) "http://mysite.com/selected/url/"
  ["title"]=>
  string(10) "Link Title"
  ["target"]=>
  string(6) "_blank"
  ["postid"]=>
  int 2231
}`

== Changelog ==

= 1.2.2 =
* New handlers for the updated link picker with WP 4.5.

= 1.2.1 =
* Attempt to add a post ID ($link["postid"]) to the field data

= 1.2 =
* Automatically update the link title when clicking on a link.  This functionality differs from the WYSIWYG link picker (which assumes highlighted text) but should be consistent with expected behavior of an ACF field.

= 1.1.2 =
* Added NL translation support from [vjanssens](https://github.com/vjanssens)

= 1.1.1 =
* Added PT translation support from [alvarogois](https://github.com/alvarogois)
* Bumped compatibility information

= 1.1 =
* Bump version, preserve _blank target if set from [philmprice](https://github.com/philmprice)

= 1.0.3 =
* Translation support from [m0n0mind](https://github.com/m0n0mind)

= 1.0.2 =
* Forked by ahebrank and refactored, updated for compatibility with WP 4.2

= 1.0.1 =
* Solve bug with repeater fields (credit to Willy Bahuaud http://wabeo.fr/)
* Solve problem with empty values (credit to Willy Bahuaud http://wabeo.fr/)

= 1.0.0 =
* Initial Release.

== Upgrade Notice ==

= 1.1 =
Adds target attribute preservation

= 1.0.3 =
Adds German translation support

= 1.0.2 =
Adds WP 4.2+ support
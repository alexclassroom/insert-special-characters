# Insert Special Characters

![Insert Special Characters](https://github.com/10up/insert-special-characters/blob/develop/.wordpress-org/banner-1544x500.png)

[![Support Level](https://img.shields.io/badge/support-stable-blue.svg)](#support-level) ![Required PHP Version](https://img.shields.io/wordpress/plugin/required-php/insert-special-characters?label=Requires%20PHP) ![Required WP Version](https://img.shields.io/wordpress/plugin/wp-version/insert-special-characters?label=Requires%20WordPress) ![WordPress tested up to version](https://img.shields.io/wordpress/plugin/tested/insert-special-characters?label=WordPress) [![GPLv2 License](https://img.shields.io/github/license/10up/insert-special-characters.svg)](https://github.com/10up/insert-special-characters/blob/develop/LICENSE.md) [![Dependency Review](https://github.com/10up/insert-special-characters/actions/workflows/dependency-review.yml/badge.svg)](https://github.com/10up/insert-special-characters/actions/workflows/dependency-review.yml) [![E2E test](https://github.com/10up/insert-special-characters/actions/workflows/cypress.yml/badge.svg)](https://github.com/10up/insert-special-characters/actions/workflows/cypress.yml) [![ESLint](https://github.com/10up/insert-special-characters/actions/workflows/eslint.yml/badge.svg)](https://github.com/10up/insert-special-characters/actions/workflows/eslint.yml) [![PHPCS](https://github.com/10up/insert-special-characters/actions/workflows/phpcs.yml/badge.svg)](https://github.com/10up/insert-special-characters/actions/workflows/phpcs.yml) [![PHP Compatibility](https://github.com/10up/insert-special-characters/actions/workflows/php-compatibility.yml/badge.svg)](https://github.com/10up/insert-special-characters/actions/workflows/php-compatibility.yml) [![CodeQL](https://github.com/10up/insert-special-characters/actions/workflows/codeql-analysis.yml/badge.svg)](https://github.com/10up/insert-special-characters/actions/workflows/codeql-analysis.yml) [![WordPress Plugin Version](https://img.shields.io/wordpress/plugin/v/insert-special-characters?logo=wordpress&logoColor=FFFFFF&label=Playground%20Demo&labelColor=3858E9&color=3858E9)](https://playground.wordpress.net/?blueprint-url=https://raw.githubusercontent.com/10up/insert-special-characters/develop/.wordpress-org/blueprints/blueprint.json)

> A Special Character inserter for the WordPress block editor (Gutenberg).

## Overview

Ever wanted to add a special character while working within Gutenberg and suddenly find yourself longing for the days of the Classic Editor and the Special Character inserter?  Well long no more, the Insert Special Characters plugin is here to ease your publishing woes!

**Note:** you can display the popover via the `ctrl`/`cmd` + `o` keyboard shortcut.

![Demo of special characters within Gutenberg](.wordpress-org/screenshot-1.gif "Example of special characters selection in the Block Editor")

## Extending

To control the available tabs and characters, developers can filter the data set using the `insertspecialcharacters-characters` JavaScript (`wp.hooks`) filter.

For example, to create a character inserter that only provides currency symbols:

```js
wp.hooks.addFilter(
	'insertspecialcharacters-characters',  // The filter name.
	'mycallback', // Our callback namespace.
	function( component ) { // The callback function.

		// Return the categories/characters to display.
		// The data structure is: { category: [ character data ], category2: ... }
		return {
			"Currency": [
				{ "entity": "&dollar;", "hex": "&#0024;", "name": "Dollar Sign", "char": "$" },
				{ "entity": "&euro;", "hex": "&#20AC;", "name": "Euro Sign", "char": "€" },
				{ "entity": "&cent;", "hex": "&#00A2;", "name": "Cent Sign", "char": "¢" },
				{ "entity": "&pound;", "hex": "&#00A3;", "name": "Pound Sign", "char": "£" },
				{ "entity": "&yen;", "hex": "&#00A5;", "name": "Yen Sign", "char": "¥" },
			]
		};
	}
);
```

## Requirements

* PHP 7.4+
* [WordPress](http://wordpress.org/) 6.1+

## Installation

1. Install the plugin via the plugin installer, either by searching for it or uploading a .zip file.
1. Activate the plugin.
1. Use Insert Special Characters!

## Development

1. Clone this repo into your `wp-content/plugins` folder: `git clone https://github.com/10up/insert-special-characters.git`
2. Build the plugin by running the following NPM commands in the plugin folder.
	* `npm install && composer install`
	* `npm run build`
3. Activate the `Insert Special Characters` plugin.

## Frequently Asked Questions

### How come I do not see all the special characters?
When a character is displayed using a font that doesn't support that character, a default "not defined" glyph from that font is used. The "not defined" glyph in most fonts has the appearance of a rectangular box, or some variation of that.

One example of a font with support for wide range of glyphs is the [Noto](https://fonts.google.com/noto) family by Google Fonts, which can be loaded by the theme to render the missing characters.

## Support Level

**Stable:** 10up is not planning to develop any new features for this, but will still respond to bug reports and security concerns. We welcome PRs, but any that include new features should be small and easy to integrate and should not include breaking changes. We otherwise intend to keep this tested up to the most recent version of WordPress.

## Changelog

A complete listing of all notable changes to Insert Special Characters are documented in [CHANGELOG.md](https://github.com/10up/insert-special-characters/blob/develop/CHANGELOG.md).

## Contributing

Please read [CODE_OF_CONDUCT.md](https://github.com/10up/insert-special-characters/blob/develop/CODE_OF_CONDUCT.md) for details on our code of conduct, [CONTRIBUTING.md](https://github.com/10up/insert-special-characters/blob/develop/CONTRIBUTING.md) for details on the process for submitting pull requests to us, and [CREDITS.md](https://github.com/10up/insert-special-characters/blob/develop/CREDITS.md) for a listing of maintainers of, contributors to, and libraries used by Insert Special Characters.

## Like what you see?

<a href="http://10up.com/contact/"><img src="https://10up.com/uploads/2016/10/10up-Github-Banner.png" width="850" alt="Work with us at 10up"></a>

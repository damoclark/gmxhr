# README

[![NPM](https://nodei.co/npm/gmxhr.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/gmxhr/)

## Description

`gmxhr` is a `xmlHttpRequest` API wrapper for Greasemonkey's
[GM_xmlhttpRequest](https://wiki.greasespot.net/GM_xmlhttpRequest)
function.

It provides a xmlHttpRequest API to the `GM_xmlhttpRequest` function from the
[Greasemonkey](https://addons.mozilla.org/en-US/firefox/addon/greasemonkey/) and
[Tampermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en)
WebExtensions for Firefox and Chromium-based browsers. This means it can be used
as a drop-in replacement for higher-level libraries and frameworks for the
standard xmlHttpRequest class.

## Installation

```bash
$ npm install gmxhr
```

## Usage

As an example, `gmxhr` can be used to allow jQuery to perform ajax calls using
`GM_xmlhttpRequest` within a userscript:

```javascript
var gmxhr = require('gmxhr');

....

$.ajax({
	url: '/p/',
	xhr: function(){return new gmxhr();},
	type: 'POST',
  success: function(val){
		....
	}
 });
```

## Attribution

My thanks to Ryan Greenberg and Martin Monperrus for
[creating](http://ryangreenberg.com/archives/2010/03/greasemonkey_jquery.php)
and [sharing](https://gist.github.com/monperrus/999065) this code.  
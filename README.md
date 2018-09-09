# README

[![NPM](https://nodei.co/npm/gmxhr.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/gmxhr/)

## Description

`gmxhr` is a `xmlHttpRequest` API wrapper for Greasemonkey (and derivative) userscript engine's
[GM_xmlhttpRequest](https://wiki.greasespot.net/GM_xmlhttpRequest)
function.

It provides a `xmlHttpRequest` API to the `GM_xmlhttpRequest` function from the
legacy [Greasemonkey v3](https://addons.mozilla.org/en-US/firefox/addon/greasemonkey/) and
[Tampermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en)
WebExtensions for Firefox and Chromium-based browsers. 

It is also compatible with the [new Greasemonkey 4 API](https://www.greasespot.net/2017/09/greasemonkey-4-for-script-authors.html)
using `GM.xmlHttpRequest`.

This means it can be used as a drop-in replacement for higher-level libraries and frameworks for the
standard xmlHttpRequest class, including [superagent](https://github.com/damoclark/superagent-gmxhr) and 
[axios](https://github.com/damoclark/axios-gmxhr-adapter).

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
# short-uuid
[![Build Status](https://travis-ci.org/oculus42/short-uuid.svg?branch=master)](https://travis-ci.org/oculus42/short-uuid) 
[![Code Climate](https://codeclimate.com/github/oculus42/short-uuid/badges/gpa.svg)](https://codeclimate.com/github/oculus42/short-uuid) 
[![Test Coverage](https://codeclimate.com/github/oculus42/short-uuid/badges/coverage.svg)](https://codeclimate.com/github/oculus42/short-uuid/coverage) 
[![Dependencies](https://david-dm.org/oculus42/short-uuid.svg)](https://david-dm.org/oculus42/short-uuid)

Generate and translate standard UUIDs into shorter - or just *different* - formats and back.

## v2.3.1

short-uuid provides RFC4122 v4-compliant UUIDs,
thanks to [`uuid`](https://github.com/kelektiv/node-uuid).

It includes Browserify support for client-side use as proposed by [voronianski](https://github.com/voronianski),
with compiled browser-ready files in the npm package for convenience. The library is exposed as `ShortUUID`.

2.3.0 corrects [Snyk](https://snyk.io) vulnerability protection to a dev dependency.
2.3.1 merges the 2.1.x fixes into version history.

### v2.2.0 Deprecated
2.2.0 incorrectly added Snyk as a production dependency. It has been deprecated.

```javascript
var short = require('short-uuid');
var translator = short(); // Defaults to flickrBase58
var decimalTranslator = short("0123456789"); // Provide a specific alphabet for translation
var cookieTranslator = short(short.constants.cookieBase90); // Use a constant for translation

// Generate a shortened v4 UUID
translator.new();

// Generate plain UUIDs
short.uuid(); // From the constructor without creating a translator
translator.uuid(); // Each translator provides the uuid.v4() function

// Translate UUIDs
translator.toUUID(shortId);
translator.fromUUID(regularUUID);

// See the alphabet used by a translator
translator.alphabet

// View the constants
short.constants.flickrBase58;
short.constants.cookieBase90;

```

v2.3.1 is under 1K when compressed. Using Browserify, the library and dependencies are ~3.2K.

Please see [Revisions](revisions.md) for information on previous versions.

# Firefox App Validator: Manifest

[![Build Status](https://secure.travis-ci.org/mozilla/node-firefox-app-validator-manifest.png)](http://travis-ci.org/mozilla/node-firefox-app-validator-manifest)

## What it is

This is the Firefox App manifest validator for verifying that your `manifest.webapp` file has the correct information before submitting to the [Firefox Marketplace](https://marketplace.firefox.com).

## Setup

    git clone git@github.com:mozilla/node-firefox-app-validator-manifest.git
    cd node-firefox-app-validator-manifest
    npm install

## Checking your manifest: an example

    var fs = require('fs');
    var Manifest = require('firefox-app-validator-manifest');
    var ff = new Manifest();

    fs.readFile('manifest.webapp', 'utf8', function (err, data) {
      if (!err) {
        var results = ff.validate(data, options);

        // If there are any errors or warnings, this will have them listed.
        console.log(results);
      }
    });

`options` contains the app resource keys of: `listed` and `packaged`. Defaults to `false` for both if not included.

## Tests

    # To run tests once
    npm test

    # To run tests continually on file change
    npm run-script testwatch

## License

Mozilla Public License Version 2.0

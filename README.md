# Overview

This is a skeleton project that illustrates how you can use hem to expose project
dependencies to your client side javascript via a 'require' like system.

# Pre-Reqs

You must have npm (node package manager) installed, and hem:

    1. Install [npm.js](http://npmjs.org).
    2. Install hem with npm: npm install -g hem

# Dependencies

Dependencies are managed with a combination of npm and hem. Use npm
to explicitly install all of your projects external dependencies. Use
hem to specify which dependencies (both external and local) that should
be stitched together for you client side operations.

This skeleton project has one dependency: underscore.

To 'start up' the dependencies tell npm to download all your dependencies:

    npm install

## Adding dependencies

Use npm to search for a specific dependency and then modify the package.json
file to ensure that the dependency is tracked in the future. Then specify the
dependency for your application in slug.json.

For example, suppose you wanted to add the coffee-script dependency. Just use npm 
to install the dependency and save it to your package.json file:

    1. npm --save install coffee-script
    2. Manually edit the slug.json file. Add "coffee-script" to "dependencies".

Suppose I wanted to include your own module 'bloomfilters', and it wasn't in the npm 
registry. You can add it to your project in the following way:

    1. npm --save install https://github.com/dsummersl/bloomfilters/tarball/master
    2. Manually edit the slug.json file. Add "bloomfilters" to "dependencies".

## Local modules

If you want to include your own coffee or javascript you can do so by adding
those files to the app/ folder. Note that in order to expose your script via
the 'require' method you must make it a CommonJS module. It is very simple -
see [the hem docs](http://spinejs.com/docs/hem).

## Local files

If you want to include non-CommonJS non 'require' code you can also stitch that
by referencing your custom javascript or coffeescript via the 'libs' list in
slug.json.

## CSS

Hem will stitch together your CSS to, if you want. See [the hem docs](http://spinejs.com/docs/hem).

# Building

Once you have your dependencies listed, you can use hem to stitch them all together.

    # make sure all dependencies are present:
    npm install .
    # make public/application.js
    hem build

# Notes

Hem was meant for the [spinejs](http://spinejs.com) project - but you don't
have to use it for that. Ignore any docs mentioning spine as you wish...

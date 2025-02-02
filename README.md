![FrozenJS Logo](https://secure.gravatar.com/avatar/272e5230cf45370ed751878105330f3c?s=200)
Frozen <sup>v0.4.3</sup>
========================
[![build status](https://secure.travis-ci.org/iceddev/frozen.png?branch=master)](http://travis-ci.org/iceddev/frozen)

## What is Frozen?

Frozen is an open-source HTML5 game engine delivering ease-of-use, rapid development through tooling and modularity.

Our goal is to apply techniques used in building modern webapps to game development, such as AMD modules, dependency management, build process, and project scaffolding.

## Get Frozen

* Frozen (single file - AMD loader included)<br>
[Development](https://raw.github.com/iceddev/frozen/master/dist/frozen.js.uncompressed.js) and
[Production](https://raw.github.com/iceddev/frozen/master/dist/frozen.js)

* Package Managers
	* [bower](http://bower.io/) - `bower install frozen`
	* [volo](http://volojs.org/) - `volo add iceddev/frozen`
	* [jam](http://jamjs.org/) - `jam install frozen`

_Note: We supply a jam package and specify dependencies. Although these should work for game creation using the engine, frozen cannot be built or run with jam deps only_

* Frozen Source (but don't forget your dependencies)<br>
Clone it from [github](https://github.com/iceddev/frozen) - `git clone git://github.com/iceddev/frozen`<br>
or grab the zip: [Frozen Source](https://github.com/iceddev/frozen/archive/master.zip) <br>

## Getting Started

We provide both a [yeoman](http://yeoman.io/) generator and a [volo](http://volojs.org/#create) project scaffolding

### Yeoman Generator

1. `npm install -g yo grunt-cli bower generator-frozen` - Install yo, grunt-cli, bower, and generator-frozen
2. `mkdir your_game` - Create a new directory for your game
3. `cd your_game` - Enter directory for you game
4. `yo frozen` - Answer a few questions, scaffold a new game and install all dependencies
5. `grunt` - Starts a static server with live reloading and opens your browser to your game

### Volo Create

1. `npm install -g volo` - Install volo
2. `volo create your_game frozenjs/boilerplate` - Scaffold a new game and install all dependencies
3. `volo grunt` - Starts a static server with live reloading and opens your browser to your game

## Documentation

Documentation is available at http://frozenjs.com/docs/

## Examples

Play examples at http://frozenjs.com/examples/<br>
Examples source code can be found at https://github.com/iceddev/frozen/tree/master/examples

## Source

Source available on github: https://github.com/iceddev/frozen

## Browser Support

We have tested in:

* Chrome 27 & 30-canary
* Firefox 21 & 22
* IE10 (sound with supported codecs)
* Safari 6.0.3
* Chrome for Android 27 & Beta 28 (limited sound support) - Suggestion: in `chrome://flags`, turn on "Disable gesture requirement for media playback" & "Enable WebAudio"
* Firefox for Android 22 & Beta 23 (Doesn't load some Box2d examples - unsure why)
* PhantomJS 1.9.1

__Most modern browsers should support this game engine if they support requestAnimationFrame or canvas, but YMMV with sounds__

## Rapid Development Through Tooling

Our Frozen Box2d Editor is available at http://phated.github.com/frozen-editor/

Yeoman generator can be found at https://github.com/frozenjs/generator-frozen

Volo boilerplate can be found at https://github.com/frozenjs/boilerplate

## Technologies behind Frozen

While builds of Frozen may be tiny, we use some libraries and technologies behind the scenes as to not reinvent the wheel.

These technologies include:

* [Node.js](http://nodejs.org/) and [npm](https://npmjs.org/) - used for dependecy mangement for our build process and development workflow
* [Grunt](http://gruntjs.com/) - task runner for our development workflow, and allows for a single entry point into development configuration
* [Volo](http://volojs.org/) - clientside dependency management and project scaffolding tool
* [Lo-Dash](http://lodash.com/) - low-level utility library used inside the library
* [Hammer.js](http://eightmedia.github.io/hammer.js/) - multi-touch library used for mouse/touch/pointer event normalization and gestures
* [dcl](http://www.dcljs.org/) - used for generating constructors and supplying AOP convenience methods
* [Box2d](https://box2dweb.googlecode.com/) - used for physics calculations in games
* [Dojo](http://dojotoolkit.org/) - used for AMD loader and some utility modules inside the library, Dojo build process is used to build a single JS file
* [JSDoc](http://usejsdoc.org/) - generates documentation for code
* [Jasmine](http://pivotal.github.com/jasmine/) - tests all use Jasmine
* [AMD](http://requirejs.org/docs/whyamd.html) - all modules are written with AMD and the single layer includes an AMD module loader

## Development

### Dependencies

All development tasks depend on having dependencies installed.

Use `npm install` to get all the build process dependencies
Use `volo add` to get all the library dependencies

### Building the dist/frozen layer

`grunt build` to lint, test, doc, and run dojo build process to build the single layer

### Generating the docs

`grunt docs` will lint and generate docs

### Running the tests

`grunt test` to lint, run tests in PhantomJS and open your default browser at the test URL

### Linting the project

`grunt jshint:all` to lint the project

### Building when files change

`grunt watch:all` to execute `grunt build` whenever a file changes

## Release Notes

### <sup>v0.4.3</sup>

__Bug Fixes__

* Updated to the newest WebAudio spec

### <sup>v0.4.2</sup>

__Breaking Changes__

* None! This is a bug fix release

__New Features__

* Fixed rotation property on entities

__Non-Breaking Changes__

* Update Lo-Dash dependency location
* Remove extra call to `loadResources` in `GameCore#run`

__Deprecations__

* None! This is a bug fix release

### <sup>v0.4.1</sup>

__Breaking Changes__

* None! This is a bug fix release

__New Features__

* Yeoman generator support!!! See https://github.com/frozenjs/generator-frozen
* Box now handles sensors! Just add sensor property to your entities and they will start showing up in your collision handlers
* Added Gamepad API example

__Non-Breaking Changes__

* Fix bug where `GameCore.stop` didn't actually stop a game
* Disable `prevent_default` option on default Hammer.js configuration inside `InputManager` - it caused problems with click events on DOM elements
* Fix error on Chrome for Android when there was no WebAudio is available

__Deprecations__

* None! This is a bug fix release

Full changelog available: [Changelog](https://github.com/iceddev/frozen/wiki/Changelog)

## License

The MIT License (MIT)

Copyright (c) 2013 Iced Development, LLC

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

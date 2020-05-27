# emits-change

[![Latest Version on NPM](https://img.shields.io/npm/v/emits-change.svg?style=flat-square)](https://npmjs.com/package/emits-change)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)
[![Build Status](https://img.shields.io/travis/spatie/emits-change.svg?style=flat-square)](https://travis-ci.org/spatie/emits-change)
[![Code Climate](https://img.shields.io/codeclimate/github/spatie/emits-change.svg?style=flat-square)](https://img.shields.io/codeclimate/github/spatie/emits-change.svg)

Plug-and-play node.js events integration to emit change events.

## Support us

Learn how to create a package like this one, by watching our premium video course:

[![Laravel Package training](https://spatie.be/github/package-training.jpg)](https://laravelpackage.training)

We invest a lot of resources into creating [best in class open source packages](https://spatie.be/open-source). You can support us by [buying one of our paid products](https://spatie.be/open-source/support-us).

We highly appreciate you sending us a postcard from your hometown, mentioning which of our package(s) you are using. You'll find our address on [our contact page](https://spatie.be/about-us). We publish all received postcards on [our virtual postcard wall](https://spatie.be/open-source/postcards).

## Installation

```bash
npm install emits-change
```

This package uses the [node.js events API](https://nodejs.org/api/events.html). Make sure your javascript bundler can handles importing core node modules (e.g. Browserify does this).

## Postcardware

You're free to use this package (it's [MIT-licensed](LICENSE.md)), but if it makes it to your production environment you are required to send us a postcard from your hometown, mentioning which of our package(s) you are using.

Our address is: Spatie, Samberstraat 69D, 2060 Antwerp, Belgium.

The best postcards will get published on the open source page on our website.

## Usage

Calling `emitsChange` on an object will add node's EventEmitter, a `listen`, an `unlisten` and an `emitChange` function to the prototype.

```es6
import emitsChange from 'emits-change'

class Emitter {
    constructor() {
        emitsChange(this)
    }
}

let emitter = new Emitter

function doSomethingOnChange() {
    console.log('hodor')
}

emitter.listen(doSomethingOnChange)

emitter.emitChange()
// => hodor

emitter.unlisten(doSomethingOnChange)

emitter.emitChange()
// => *nothing*
```

## Testing

You can run the tests (ESLint & Mocha) with:

```bash
npm run test
```

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Security

If you discover any security related issues, please email [freek@spatie.be](mailto:freek@spatie.be) instead of using the issue tracker.

## Credits

- [Sebastian De Deyne](https://github.com/sebastiandedeyne)
- [All Contributors](../../contributors)

## About Spatie

Spatie is a webdesign agency in Antwerp, Belgium. You'll find an overview of all our open source projects [on our website](https://spatie.be/opensource).

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

# Elm Coverage [![Build Status](https://travis-ci.org/zwilias/elm-coverage.svg?branch=master)](https://travis-ci.org/zwilias/elm-coverage) [![Build status](https://ci.appveyor.com/api/projects/status/xsarefeowsmffnny?svg=true)](https://ci.appveyor.com/project/zwilias/elm-coverage) [![Documentation Status](https://readthedocs.org/projects/elm-coverage/badge/?version=latest)](http://elm-coverage.readthedocs.io/en/latest/?badge=latest)
> Work in progress - Code coverage tooling for Elm

`elm-coverage` is a tool for calculating code coverage for Elm code tested with
`elm-test`.

The goal of the reports generated by `elm-coverage` is to help you visualize
what parts of your code are being evaluated when running your tests, and to try
and guide you towards writing tests that focus specifically on the more complex
functions in your codebase.

The goal is **not** to condense that information down into a single metric. It
is too easy to write tests that don't make meaningful assertions about your code
and its behaviour, but only serve to increase the coverage.

The only thing worse than having no tests is having tests that provide a false
sense of security.

For further reading, please direct yourself to https://elm-coverage.readthedocs.io

Installation
------------

Installing `elm-coverage` works much the same way as installing other tools in
the Elm ecosystem:

    npm i -g elm-coverage

Usage
-----

The simplest invocation of `elm-coverage` is to simply invoke `elm-coverage` in
the root of your project:

    elm-coverage

By default, `elm-coverage` assumes that you have `elm-test` installed globally,
and that `elm-test` needs no further, special flags.

You can specify an alternative path to the root directory (where elm-coverage
will search for the `elm.json` file):

    elm-coverage src/elm-widget/

If you don't want to use a globally installed `elm-test`, you can specify the
path to an `elm-test` executable:

    elm-coverage --elm-test ./node_modules/.bin/elm-test

Parameters following `--` are passed through to `elm-test`, for example to
specify the initial `seed` and number of `fuzz` testruns:

    elm-coverage -- --seed 12345 --fuzz 99

`elm-coverage` will write an HTML report to `.coverage/coverage.html`. It is not
recommended to version control this directory. In order to open the report once
it is generated, you can specify the `--open` option:

    elm-coverage --open

Contribute
----------

Issues and source code is available [on
github](https://github.com/zwilias/elm-coverage>). The source for
`elm-instrument` which is used to actually instrument the sources in order to
calculate coverage is also
[available](https://github.com/zwilias/elm-instrument).

License
-------

`elm-coverage` is licensed under the BSD-3 license. `elm-instrument` is
licensed under the BSD-3 license.

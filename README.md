# Pact Mock Service

[![Build Status](https://travis-ci.org/pact-foundation/pact-mock_service.svg?branch=master)](https://travis-ci.org/pact-foundation/pact-mock_service)

This codebase provides the mock service used by implementations of [Pact][pact]. It is packaged as a gem, and as a standalone executable for Mac OSX and Linux and Windows.

The mock service provides the following endpoints:

* DELETE /interactions - clear previously mocked interactions
* POST /interactions - set up an expected interaction
* GET /interactions/verification - determine whether the expected interactions have taken place
* POST /pact - write the pact file

As the Pact mock service can be used as a standalone executable and administered via HTTP, it can be used for testing with any language. All that is required is a library in the native language to create the HTTP calls listed above. Check out [docs.pact.io](https://docs.pact.io) for a list of implemented languages. If you are interested in creating bindings in a new langauge, and have a chat to one of us on the [pact-dev Google group][pact-dev].

## Usage

For some examples of the HTTP requests that occur under the hood when using either the Ruby client or the Javascript client, see this [gist](https://gist.github.com/bethesque/9d81f21d6f77650811f4).

### Mac OSX, Linux and Windows, without Ruby

See the [releases][releases] page for the latest standalone executables.

### With Ruby on Mac OSX and Linux

    $ gem install pact-mock_service
    $ pact-mock-service --port 1234

Run `pact-mock-service help` for command line options.

### With Ruby on Windows

Check out the wiki page [here][install-windows].

#### With SSL

If you need to use the mock service with HTTPS, you can use the built-in SSL mode which relies on and generates a self-signed certificate.

    $ pact-mock-service --port 1234 --ssl

If you need to provide your own certificate and key, use the following syntax.

    $ pact-mock-service --port 1234 --ssl --sslcert PATH_TO_CERT --sslkey PATH_TO_KEY

## Contributing

See [CONTRIBUTING.md](/CONTRIBUTING.md)

[pact]: https://github.com/realestate-com-au/pact
[releases]: https://github.com/pact-foundation/pact-mock_service/releases
[javascript]: https://github.com/DiUS/pact-consumer-js-dsl
[pact-dev]: https://groups.google.com/forum/#!forum/pact-dev
[install-windows]: https://github.com/bethesque/pact-mock_service/wiki/Installing-the-pact-mock_service-gem-on-Windows
[why-generated]: https://github.com/realestate-com-au/pact/wiki/FAQ#why-are-the-pacts-generated-and-not-static

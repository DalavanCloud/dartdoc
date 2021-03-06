# Contribute to dartdoc

To _use_ the dartdoc tool, see the [user docs][]. This page contains
information relevant for contributors to the dartdoc project.

## Can I help?

Yes!

Start by [using the tool](README.md) and filing issues and requests.

See the [dartdoc API](https://pub.dartlang.org/documentation/dartdoc/latest/) docs, generated by
dartdoc.

If you want to contribute, check out the [issue tracker][] and see if there's an
issue that you're passionate about. If you want to add a new feature that's not
yet in the issue tracker, start by opening an issue. Thanks!

[![Build Status](https://travis-ci.org/dart-lang/dartdoc.svg)](https://travis-ci.org/dart-lang/dartdoc)
[![Build status](https://ci.appveyor.com/api/projects/status/s6sh69et2ga00dlu?svg=true)](https://ci.appveyor.com/project/devoncarew/dartdoc)

## Making Changes

1. `grind` is needed to run dartdoc integration tests, see installed via `pub global activate grinder`.
2. When a change is user-facing, please add a new entry to the [changelog](https://github.com/dart-lang/dartdoc/blob/master/CHANGELOG.md)
3. Please include a test for your change.  `dartdoc` has both `package:test`-style unittests as well as integration tests.  To run the unittests, use `grind test`.
4. For major changes, run `grind compare-sdk-warnings` and `grind compare-flutter-warnings`, and include the summary results in your pull request.
5. Be sure to format your Dart code using `dartfmt -w`, otherwise travis will complain.
6. Post your change via a pull request for review and integration!

## Testing

dartdoc has a number of grinder utility methods that can be used to check for behavior changes
or try out your change on arbitrary packages. 

```bash
# Serve the latest version of the given package locally on port 9000.
PACKAGE_NAME=angular_components grind serve-pub-package

# Build the SDK docs with the head version and compare its warning
# output and (rough) performance to the main version.
grind compare-sdk-warnings

# Serve the flutter docs built with the head version on port 8001.
grind serve-flutter-docs

# Serve the test package (testing/test_package) on port 8002
grind serve-test-package-docs
```

There are more added all the time -- run `grind --help` to see them all.

## License

Please see the [dartdoc license](https://github.com/dart-lang/dartdoc/blob/master/LICENSE).

[user docs]: https://github.com/dart-lang/dartdoc#dartdoc
[issue tracker]: https://github.com/dart-lang/dartdoc/issues

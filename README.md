# yeoman-fountain-test
Test repo using http://fountainjs.io/

Demonstrates a possible bug where coverage reporting isn't being generated.

The [coverage](https://github.com/flacito/yeoman-fountain-test/tree/master/coverage/Chrome%2058.0.3029%20(Mac%20OS%20X%2010.12.4)) directory for Chrome was added to show the 0/0 coverage that I'm getting.

The [coverage](https://github.com/flacito/yeoman-fountain-test/tree/master/coverage/PhantomJS%202.1.1%20(Mac%20OS%20X%200.0.0)) directory for PhantomJS was added to show the good coverage that I'm getting. I don't think PhantomJS matters, it's just that I changed to it for CI.

These are the steps to recreate:
1. Run the generator choosing Angular2, WebPack with NPM, TypeScript,
  SASS, and TravisCI
1. Run `gulp test`
1. Note that the coverage report isn't reporting any coverage

I eventually want to use the [Karma coverage threshold reporter](https://github.com/lithiumtech/karma-threshold-reporter) to fail the build
if the coverage we desire isn't met.  With the way the coverage report is
being generated, it's always 100% coverage.

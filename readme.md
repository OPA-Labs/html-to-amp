# html-to-amp [![Build Status](https://travis-ci.org/micnews/html-to-amp.png?branch=master)](https://travis-ci.org/micnews/html-to-amp)

Small module to transform html pages to amp, using [html-to-article-json](https://www.npmjs.com/package/html-to-article-json) &amp; [article-json-to-amp](https://www.npmjs.com/package/article-json-to-amp)

## Installation

Download node at [nodejs.org](http://nodejs.org) and install it, if you haven't already.

```sh
npm install html-to-amp --save
```

## Usage

```js
import htmlToAmp from 'html-to-amp';

const html = `
  <p>beep booop</p>
  // if width and/or height is missing of an image the width & height will be
  //  read from the image (since width & height is required in AMP)
  <img src="http://example.com/image.jpg" />

  // youtube, twitter, instagram, facebook, vine & custom embeds are
  //  (through html-to-article-json) supported
  <blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr"><a href="https://t.co/kt1c5RWajI">https://t.co/kt1c5RWajI</a>’s <a href="https://twitter.com/david_bjorklund">@david_bjorklund</a> published 2 node modules to convert HTML snippets to <a href="https://twitter.com/AMPhtml">@amphtml</a><a href="https://t.co/yB5KMDijh6">https://t.co/yB5KMDijh6</a></p>&mdash; Malte Ubl (@cramforce) <a href="https://twitter.com/cramforce/status/697485294531145730">February 10, 2016</a></blockquote> <script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
`;

// can be used with callbacks
htmlToAmp(html, (err, amp) => {
  if (err) {
    throw err;
  }
  // do something with it
});

// when second argument is ommited a promise is returned
htmlToAmp(html).then(amp => {
  // do something with it
});

```

## Tests

```sh
npm install
npm test
```

## Dependencies

- [article-json-to-amp](https://github.com/micnews/article-json-to-amp): Render JSON formatted article in the AMP format
- [bluebird](https://github.com/petkaantonov/bluebird): Full featured Promises/A+ implementation with exceptionally good performance
- [html-to-article-json](https://github.com/micnews/html-to-article-json): Converting HTML to article-json
- [request-image-size](https://github.com/FdezRomero/request-image-size): Detect image dimensions via request.

## Dev Dependencies

- [ava](https://github.com/sindresorhus/ava): Futuristic test runner 🚀
- [babel-cli](https://github.com/babel/babel/tree/master/packages): Babel command line.
- [babel-core](https://github.com/babel/babel/tree/master/packages): Babel compiler core.
- [babel-preset-es2015](https://github.com/babel/babel/tree/master/packages): Babel preset for all es2015 plugins.
- [nyc](https://github.com/bcoe/nyc): a code coverage tool that works well with subprocesses.
- [package-json-to-readme](https://github.com/zeke/package-json-to-readme): Generate a README.md from package.json contents
- [semistandard](https://github.com/Flet/semistandard): All the goodness of `feross/standard` with semicolons sprinkled on top.
- [snazzy](https://github.com/feross/snazzy): Format JavaScript Standard Style as Stylish (i.e. snazzy) output


## License

MIT

_Generated by [package-json-to-readme](https://github.com/zeke/package-json-to-readme)_

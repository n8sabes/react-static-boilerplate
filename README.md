This fork is purely for demonstrating an issue with rendering a background image from css.

Turns out, this is a known webpack problem. Here is a temporary workaround, but you have to rebuild anytime you change the publicURL (or port). Additionally, it only works with relative paths, not absolute paths in RSB.

Workaround:

1. `webpack.config.js` must set the publicURL to the full path. `publicPath: 'http://localhost:3000/dist/'`, but this doesn't work serving it up from another port.
2. I've gotten the url to work with a relative path, but not an absolute path. `background-image: url("../../public/assets/bg_pattern.jpg");`

A few discussions on the issue:

[sourceMap css does not function for background-image (maybe stylus-loader issue)](https://github.com/webpack/css-loader/issues/29)

[Generated image urls *must* be absolute for style!css?sourceMap to work?](https://github.com/webpack/style-loader/issues/55)

[Webpack - background images not loading](http://stackoverflow.com/questions/37288886/webpack-background-images-not-loading)

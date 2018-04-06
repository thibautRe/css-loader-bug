## `css-loader` bug

Steps to reproduce the bug:

`npm i`
`npm run build`

An error is thrown:

```
ERROR in ./node_modules/css-loader?{"importLoaders":1,"sourceMap":true,"modules":true,"minimize":true}!./node_modules/postcss-loader/lib?{}!./node_modules/fyndiq-component-dropdown/styles.css
Module not found: Error: Can't resolve './fyndiq-styles-colors/colors.css' in '/Users/thibaut.remy/git/test/css-loader-bug/node_modules/fyndiq-component-dropdown'
@ ./node_modules/css-loader?{"importLoaders":1,"sourceMap":true,"modules":true,"minimize":true}!./node_modules/postcss-loader/lib?{}!./node_modules/fyndiq-component-dropdown/styles.css 3:10-189
@ ./node_modules/css-loader??ref--0-1!./node_modules/postcss-loader/lib??ref--0-2!./styles.css
```

The commit introducing the bug is [this one](https://github.com/webpack-contrib/css-loader/pull/698/commits/585b58b4af9b56ca9e771c4bb6ebdf1845bfcd8a). You can install the version of css-loader before this commit and it works fine

````
npm i css-loader@0.28.10
npm run build
```

This command runs just fine

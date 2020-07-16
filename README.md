# Webpack Configuration

![Webpack Image](https://raw.githubusercontent.com/webpack/media/master/logo/icon.png)

## Requirements

- @babel/core
- @babel/preset-env
- babel-loader
- css-loader
- html-loader
- html-webpack-plugin
- style-loader
- webpack
- webpack-cli
- webpack-dev-server
- webpack-merge

## Installation

**using Node Package Manager (npm)**

```
npm install
```

```
npm install @babel/core @babel/preset-env babel-loader css-loader html-loader html-webpack-plugin style-loader webpack webpack-cli webpack-dev-server webpack-merge --save-dev
```

\
\
**SCSS file**
\
untuk compile dan bundle scss ke css, gunakkan loader dibawah:

```
modules:{
  rules: [
        {
          test: /\.scss$/,
          use: [
            "style-loader",
            "css-loader",
            "sass-loader"
          ],
        },
      ],
}
```

\
\
**Live Reload**
\
package untuk live reload webpack bisa menggunakkan webpack-dev-server. untuk mengintallnya menggunakkan command dibawah:

```
$ npm install webpack-dev-server --save-dev
```

jangan lupa atur juga pada file package.json

```
"scripts": {
  "start": "webpack-dev-server",
  "build": "webpack"
},
```

\
\
**Clean Webpack Plugin**\
install terlebih dahulu package clean webpack plugin

```
npm install clean-webpack-plugin --save-dev
```

kemudian tambahkan plugin pada file webpack.prod.js. seperti dibawah:

```
const CleanWebpackPlugin = require('clean-webpack-plugin');

.....
.....


plugins: [new CleanWebpackPlugin]
```

\
\
**Entry Multiple**
\
untuk entry javascript bisa menggunakkan object pada entry. kemudian pada output gunakkan [name]. [contenthash] digunakkan untuk memberikan nama dengan random pada file hasil bundle

```
entry: {
    main: "./src/app.js",
    vendor: "./src/vendor.js",
}
  output: {
    path: path.resolve(__dirname, "dist"),
    filename: "[name].[contenthash].bundle.js",
  },
```

\
\
**Mutiples HTML File**\

```
modules:{
  rules: [
        {
          test: /\.html$/,
          use: [
            {
              loader: "file-loader",
              options: [
                name : "[name].[ext]"
              ]
            }
          ],
          exclude: path.resolve(__dirname, "src/index.html")
        },
      ],
}
```

**Asset**

Done!

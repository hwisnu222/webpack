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

**Entry Multiple**
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

Done!

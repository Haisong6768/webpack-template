# webpack-template

This is a quick starting template for webpack, an open-source JavaScript module bundler.

![webpack logo](https://raw.githubusercontent.com/webpack/media/master/logo/logo-on-white-bg.png "webpack logo")

For more information, please visit [webpack](https://webpack.js.org/ "webpack").

_This template could be used for projects containing HTML, CSS and plain JavaScript._

## Features

- Zero configuration for small projects.
- A dev server with auto reloading and Hot Module Replacement (HMR) is included.
- All JavaScript files will be transpiled using Babel for compatibility.
- All filenames will include unique hashes for cache busting.
- Assets are automatically arranged and referenced for easy exports.
- The `/dist` folder is automatically cleaned.

## Initialization

Run the following command to quickly initialize npm.

```bash
npm init -y
```

Run the following command to install all required dev dependencies.

```bash
npm install --save-dev @babel/core @babel/preset-env babel-loader clean-webpack-plugin css-loader css-minimizer-webpack-plugin html-loader html-webpack-plugin mini-css-extract-plugin style-loader webpack webpack-cli webpack-dev-server
```

Paste the following scripts into `"scripts"` in `package.json`.

```json
"prod": "webpack --config webpack.prod.js",
"build": "webpack --config webpack.dev.js",
"dev": "webpack-dev-server --config webpack.dev.js"
```

## Usage

- Run `npm run dev` to enable dev server on localhost:6768 (port configurable). This server will watch for file changes in the `/src` directory and recompile each time. All files will be stored in memory and served, so that no files will be created.
- Run `npm run build` to compile once, files will be stored in the `/dist` directory. No CSS files will be generated, as they are contained inside JavaScript files and injected into the DOM once the page is loaded. No code will be minified for clear readability during development.
- Run `npm run prod` to compile once, files will be stored in the `/dist` directory. All code will be minified for minimum size when shipping.

## Notes

- Place your source files inside the `/src` directory.
- For absolute beginners, press Ctrl/Cmd + C to terminate the dev server.
- Configurations for development(`npm run dev` and `npm run build`) are contained in the `webpack.dev.js` file.
- Configurations for production(`npm run prod`) are contained in the `webpack.prod.js` file.
- Multiple JavaScript files entry points can be added to the `entry` property in the form of `name: path`.
  - e.g.
    ```
    entry: {
        main: "./src/main.js",
        vendor: "./src/vendor.js"
    }
    ```
- Multiple HTML files can be added by instantiating the `HtmlWebpackPlugin` multiple times.
  - e.g.
    ```
    plugins: [
        new CleanWebpackPlugin(),
        new HtmlWebpackPlugin({
            template: "./src/index.html",
            filename: "index.html",
        }),
        new HtmlWebpackPlugin({
            template: "./src/about.html",
            filename: "about.html",
        })
    ]
    ```
- Remember to modify the `.gitignore` file if you would like to use Git for version control.

Thank you!

Regards,
Haisong

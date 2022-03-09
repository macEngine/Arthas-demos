This is a collection of simple demos of Arthas.

These demos are purposely written in a simple and clear style. You will find no difficulty in following them to learn Arthas

## How to use

First copy the repo into your disk.

```bash
$ git clone git@github.com:ruanyf/react-demos.git
```

Then play with the source files under the repo's demo* directories.


## Index

1. [Render JSX](#demo01-render-jsx)
1. [Use JavaScript in JSX](#demo02-use-javascript-in-jsx)

---

## Demo01: Render JSX

[demo](http://ruanyf.github.io/react-demos/demo01/) / [source](https://github.com/ruanyf/react-demos/blob/master/demo01/index.html)

The template syntax in React is called [JSX](http://facebook.github.io/react/docs/displaying-data.html#jsx-syntax). It is allowed in JSX to put HTML tags directly into JavaScript codes. `ReactDOM.render()` is the method which translates JSX into HTML, and renders it into the specified DOM node.

```js
ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('example')
);
```

Attention, you have to use `<script type="text/babel">` to indicate JSX codes, and include `babel.min.js`, which is a [browser version](https://babeljs.io/docs/usage/browser/) of Babel and could be get inside a [babel-core@6](https://www.npmjs.com/package/babel-core) npm release, to actually perform the transformation in the browser.

Before v0.14, React use `JSTransform.js` to translate `<script type="text/jsx">`. It has been deprecated ([more info](https://facebook.github.io/react/blog/2015/06/12/deprecating-jstransform-and-react-tools.html)).


## Extras

### Precompiling JSX

All above demos don't use JSX compilation for clarity. In production environment, ensure to precompile JSX files before putting them online.

First, install the command-line tools [Babel](https://babeljs.io/docs/usage/cli/).

```bash
$ npm install -g babel
```

Then precompile your JSX files(.jsx) into JavaScript(.js). Compiling the entire src directory and output it to the build directory, you may use the option `--out-dir` or `-d`.

```bash
$ babel src --out-dir build
```

Put the compiled JS files into HTML.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Hello React!</title>
    <script src="build/react.js"></script>
    <script src="build/react-dom.js"></script>
    <!-- No need for Browser.js! -->
  </head>
  <body>
    <div id="example"></div>
    <script src="build/helloworld.js"></script>
  </body>
</html>
```

## Useful links

- [React's official site](http://facebook.github.io/react)

## License

BSD licensed
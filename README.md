# react-lite

## Introduction
React under 20k.
react-lite is an implementation of React that optimizes for small script size.

It supports the core APIs of React, such as Virtual DOM, intended as a drop-in
replacement for React, when you don't need server-side rendering in browser(no React.renderToString/React.renderToStaticMarkup).

If you are using webpack, it's so easy to use react-lite, just config alias in webpack.config.js:

```javascript
// webpack.config.js
{
	alias: {
		'react': 'react-lite',
		'react-dom': 'react-lite'
	}
}
```
## install

you can install react-lite from npm

```shell
npm install --save react-lite
```

## documentation

you can learn react-lite from [React official documentation](http://facebook.github.io/react/)

## what can react-lite do?

just the same as what react does, see some demos below(I just add the alias to webpack.config.js, no need to do anything else):

- react-lite works with react-router: [examples](http://react-lite-with-react-router.coding.io/)
- react-lite works with redux:
	* [async](http://lucifier129.github.io/redux-examples/async/index.html)
	* [counter](http://lucifier129.github.io/redux-examples/counter/index.html)
	* [shopping-cart](http://lucifier129.github.io/redux-examples/shopping-cart/index.html)
	* [todomvc](http://lucifier129.github.io/redux-examples/todomvc/index.html)
	* [todos-with-undo](http://lucifier129.github.io/redux-examples/todos-with-undo/index.html)
- react-lite works with react-motion: [demos](https://cdn.rawgit.com/Lucifier129/react-lite/master/examples/react-motion-demos/index.html)
- js-repaint-perf(which is faster?):
	* [react](https://cdn.rawgit.com/Lucifier129/react-lite/master/examples/js-repaint-perf/react/index.html)
	* [react-lite](https://cdn.rawgit.com/Lucifier129/react-lite/master/examples/js-repaint-perf/react/lite.html)

## react-lite vs react

via react-lite:
- virtual-dom can not render to string(no React.renderToString and React.renderToStaticMarkup)
- event system is base on DOM level1(dom.onclick = handleClick)
- all of React.PropTypes method is noop(empty function)
- Do not support React-addons(for example ReactCSSTransitionGroup)
- use React in server side rendering, and use React-lite in browser
- the rule about setting props
	* if `propName in dom` is `true` then `dom[propName]=propValue`
	* else: `dom.setAttribute(propName, propValue)`

## test
react-lite reuses react's unitest(155), you can see them in `__test__`, and run the tests with:

```shell
npm test
```

License: MIT (See LICENSE file for details)

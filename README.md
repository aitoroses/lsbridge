# The Local Storage Bus

This is a fork of [lsbridge](https://github.com/krasimir/lsbridge).

1K library for exchanging messages between tabs in a same browser. It uses the local storage as a communication channel.

> The story behind the library is available [here](http://krasimirtsonev.com/blog/article/Using-Local-Storage-as-a-communication-channel).

## Usage

Add **lsbus.min.js** to your page:

```html
<script src="js/lsbus.min.js"></script>
```

There is a global object `lsbus` available.

Send messages:

```js
lsbus.send('my-namespace', { message: 'Hello world!' });
```

Listen for messages:

```js
lsbus.subscribe('my-namespace', function(data) {
  console.log(data); // prints: { message: 'Hello world!'}
});
```

Find out if `localStorage` is available:

```js
console.log(lsbus.isLSAvailable); // prints "true" or "false"
```

## Compilation

* Run `npm install` to get UglifyJS installed.
* Run `npm run-script compile` to produce `build/lsbus.min.js`

## Example

Try it yourself by opening `example/index.html` in a browser.

![lsbridge](http://work.krasimirtsonev.com/git/lsbridge/lsbridge.gif)

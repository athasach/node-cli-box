CLI Box
=======
A library to generate ASCII boxes via NodeJS

# Installation
Run the following commands to download and install the application:

```sh
$ git clone git@github.com:IonicaBizau/node-cli-box.git cli-box
$ cd cli-box
$ npm install
```

# Example
```js
// Dependencies
var Box = require("../index");

// Create a simple box
var b1 = new Box("20x10");
console.log(b1.toString());

// Set marks
var b2 = new Box({
    w: 10
  , h: 10
  , marks: {
        nw: "╔"
      , n:  "══"
      , ne: "╗"
      , e:  "║"
      , se: "╝"
      , s:  "══"
      , sw: "╚"
      , w:  "║"
      , b: "░░"
    }
});
console.log(b2.toString());

// Box with text
var b3 = new Box("20x10", "I will be \u001b[31mdis\u001b[0mplayed inside! \n A\u001b[34mnd I'm in a\u001b[0m new line!");
console.log(b3.toString());

// Box with aligned text to top-right
var b4 = new Box("30x20", {
    text: "Box content"
  , stretch: true
  , autoEOL: true
  , vAlign: "top"
  , hAlign: "right"
});
console.log(b4.toString());
```

The result will be:

![](http://i.imgur.com/lZa0XOB.png)

# Methods
## `new Box(options, text)`
Creates a new instance of Box function

### Params:
* **Object|String** *options* Object containing the options or a string
* **Object|String** *text* Object containing text and additional options or a string

### Return:
* **Object** The box instance

## `myBox.toString()`
Returns the stringified box

### Return:
* **String** Stringified box

# Changelog
## `2.0.1`
 - Updated docs.
 - Smaller boxes in tests.

## `2.0.0`
 - Added `ansi-parser` as dependency.
 - Use `ansi-parser` to work with strings containing ANSI styles.
 - Minor syntax changes.

## `1.1.0`
 - Handle colored text ([#3](https://github.com/IonicaBizau/node-cli-box/pull/3)) - Thanks [@wesolyromek](https://github.com/wesolyromek)

## `1.0.1`
 - [Fill with text feature](https://github.com/IonicaBizau/node-cli-box/pull/1)
 - Exports `defaults` in `Box.defaults`

## `1.0.0`
 - Initial release

# How to contribute

1. File an issue in the repository, using the bug tracker, describing the
   contribution you'd like to make. This will help us to get you started on the
   right foot.
2. Fork the project in your account and create a new branch:
   `your-great-feature`.
3. Commit your changes in that branch.
4. Open a pull request, and reference the initial issue in the pull request
   message.

# License
See the [LICENSE](./LICENSE) file.

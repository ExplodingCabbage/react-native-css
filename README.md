# react-native-css (and SCSS) [![Circle CI](https://circleci.com/gh/sabeurthabti/react-native-css.svg?style=svg&circle-token=a140907997e6a37c6c5ec75f04e8150cef049ff6)](https://circleci.com/gh/sabeurthabti/react-native-css) [![NPM](https://img.shields.io/npm/dm/react-native-css.svg?style=flat-square)](https://www.npmjs.com/package/react-native-css)



https://img.shields.io/npm/dm/react-native-css.svg?style=flat-square

Write your React-Native component styles in CSS/SCSS. React-native-css turns valid CSS into the Facebook subset of CSS. SCSS gives you modularity, variables, mixins and more. 

## Install

Global

```bash
npm install react-native-css -g 
```

or locally

```bash
npm install react-native-css --save
```
# Command Line Interface

React-native-css comes with a cli and you can watch a file and compile it.

``` shell
# example 1
react-native-css -i INPUT_CSS_FILE -o OUTPUT_JS_FILE --watch
```

``` shell
# example 2
react-native-css -i INPUT_CSS_FILE -o OUTPUT_JS_FILE --watch --pretty 
```

``` shell
react-native-css -i style.css -o style.js -w
```

Flags
- "-w" or "--watch" - watch for changes and recompile. 
- "-i" takes a input (optional)
- "-o" takes an output path (optional)
- "-p" or "--pretty" - pretty print the resulting compiled output

## CLI

React-native-cli doesn't use the node module ecosystem. The basic setup up is to have React-native running on one terminal, and the react-native-css on another. 
React-native-css will watch for changes and compile back to javascript.
![the workflow](http://i.imgur.com/i2OdwiY.png)

# Example

Given the following CSS:

``` css
description {
  margin-bottom: 20;
  font-size: 18;
  text-align: center;
  color: #656656;
}

container {
  padding: 30;
  margin-top: 65;
  align-items: center;
}

```

React-native-css will generate to the following:

``` javascript
// style.js
module.exports = require('react-native').StyleSheet.create(
  {"description":{"marginBottom":20,"fontSize":18,"textAlign":"center","color":"#656656"},"container":{"padding":30,"marginTop":65,"alignItems":"center"}}
  );
```

# Usage
```js
// require the generated style file
var styles = require('./style.js')
 //{"description":{"marginBottom":20,"fontSize":18,"textAlign":"center","color":"#656656"},"container":{"padding":30,"marginTop":65,"alignItems":"center"}}


class SearchPage extends Component {
  render() {
    return (
      <View style={styles.container}>
        <Text style={styles.description}>
        Buy
        </Text>

      </View>
    );
  }
}

```

* support multiple outputs
* support for custom output directory (if needed);


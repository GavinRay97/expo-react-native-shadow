# expo-react-native-shadow
[![NPM version][npm-image]][npm-url] [![Downloads][downloads-image]][npm-url]
---

This is a port of [`react-native-shadow`](https://github.com/879479119/react-native-shadow) that is **compatible with Expo** and replaces the react-native-svg tags in React Native Shadow with Expo's SVG API. **That means no ejecting!**

The documentation is the same as `react-native-shadow`'s:

![Demo](http://7xsm7w.com1.z0.glb.clouddn.com/20161015151531.png)

## HOW TO USE IT

### Installation
you must run the command to install the plugin and its dependences in you project
```bash
yarn add expo-react-native-shadow
``` 

### Implementation

1. `import { BoxShadow, BorderShadow } from 'expo-react-native-shadow'`

2. Create a styles/options object:
```js
const shadowStyle = {
  width: 100,
  height: 100,
  color: "#000",
  border: 2,
  radius: 3,
  opacity: 0.2,
  x: 0,
  y: 3,
  style: { marginVertical: 5 },
}
```

3. Wrap your component in `BoxShadow` or `BorderShadow`, passing in the `shadowStyle` object:
```js
import React, { Component } from 'react'
import { TouchableHighlight } from 'react-native'
import { BoxShadow } from 'expo-react-native-shadow'

const buttonStyle = {
  position: "relative",
  width: 160,
  height: 170,
  backgroundColor: "#fff",
}

const shadowStyle = {
  width: buttonStyle.width,
  height: buttonStyle.height,
  color: "#000",
  border: 2,
  radius: 3,
  opacity: 0.2,
  x: 0,
  y: 3,
  style: { marginVertical: 5 }
}

export default class VideoCell extends Component {
  render = () => {
    return (
      <BoxShadow setting={shadowStyle}>
        <TouchableHighlight style={buttonStyle} />
      </BoxShadow>
    )
  }
}
```

## Styles API

### BoxShadow
+ **width**: Must be set to the same value as the child component.
+ **height**: Must be set to the same value as the child component.
+ **color**: Color of shadow. **RGBA is not supported, however you may use the opacity property.**
+ **border**: Width of the shadow, cannot be a negative number.
+ **radius**: Should be set to the `borderRadius` of child component.
+ **opacity**: the `opacity` of the shadow.
+ **x**: The `offsetX` of the shadow
+ **y**: The `offsetY` of the shadow
+ **style**: A styles object to be applied to the wrapping `<View>` tag of the SVG component.

### BorderShadow
+ **width**: Same as above.
+ **color**: Same as above. 
+ **border**: Same as above.
+ **opacity**: Same as above.
+ **style**: Same as above.
+ **side**: `"top"` or `"bottom"` - Display position of the border shadow.
+ **inset**: `true` or `false` - This is similar to CSS - `shadow: color inset`


[npm-url]: https://npmjs.org/package/expo-react-native-shadow
[downloads-image]: http://img.shields.io/npm/dm/expo-react-native-shadow.svg
[npm-image]: http://img.shields.io/npm/v/expo-react-native-shadow.svg

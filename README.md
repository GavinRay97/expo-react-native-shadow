# expo-react-native-shadow
[![NPM version][npm-image]][npm-url] [![Downloads][downloads-image]][npm-url]
---

This is a port of [`react-native-shadow`](https://github.com/879479119/react-native-shadow) that is compatible with Expo and replaces the react-native-svg tags in React Native Shadow with Expo's SVG API. That means no ejecting!

The documentation is the same as `react-native-shadow`'s:


![Demo](http://7xsm7w.com1.z0.glb.clouddn.com/20161015151531.png)

## HOW TO USE IT

### Installation
you must run the command to install the plugin and its dependences in you project
```bash
yarn add expo-react-native-shadow
``` 

### Implementation

1. `import {BoxShadow} from 'expo-react-native-shadow'` (For BorderShadow, import it as 'BoxShadow')

2. Create a styles/options object:
```js
const shadowOpt = {
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

3. Wrap your component in `BoxShadow` or `BorderShadow`:
```js
import React, { Component } from 'react'
import {
  StyleSheet,
  View,
  Text,
  ScrollView,
  Image,
  TouchableHighlight
} from 'react-native'

import { BoxShadow } from 'react-native-shadow'

export default class VideoCell extends Component {
  render = () => {
    const shadowOpt = {
      width: 160,
      height: 170,
      color: "#000",
      border: 2,
      radius: 3,
      opacity: 0.2,
      x: 0,
      y: 3,
      style: { marginVertical: 5 }
    }

    return (
      <BoxShadow setting={shadowOpt}>
        <TouchableHighlight style={{
          position: "relative",
          width: 160,
          height: 170,
          backgroundColor: "#fff",
          borderRadius: 3,
          overflow: "hidden"
        }}>
      </TouchableHighlight>
      </BoxShadow>
    )
  }
}
```

## Styles API

### BoxShadow
+ **width**: you must set the value the same as your child component
+ **height**: the same as above
+ **color**: the color of shadow,it **doesn't support rgba now**,you may use opacity
+ **border**: the width of shadow , cannot less than 0
+ **radius**: the same value as the "borderRadius" of chileElement
+ **opacity**: the opacity of shadow
+ **x**: the offsetX of shadow
+ **y**: the offsetY of shadow
+ **style**: the style you want to add to the wrapper box

### BorderShadow
+ **width**,**color**,**border**,**opacity**,**style**: these attributes are the same as above
+ **side**: "top" or "bottom",you can choose where the shadow shows
+ **inset**: `true` or `false`,this is similar to CSS - `shadow: color inset`


[npm-url]: https://npmjs.org/package/react-native-shadow
[downloads-image]: http://img.shields.io/npm/dm/react-native-shadow.svg
[npm-image]: http://img.shields.io/npm/v/react-native-shadow.svg

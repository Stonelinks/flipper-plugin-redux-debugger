# Redux Debugger Plugin for Flipper

![screenshot of the plugin](https://imgur.com/QUDYozo.png)

`flipper-plugin-redux-debugger` allows you read React Native redux logs inside [Flipper](https://fbflipper.com/) now:

- Action
- State comparison

## Get Started

1. Install [redux-flipper](https://github.com/jk-gan/redux-flipper) middleware and `react-native-flipper` in your React Native app:

```bash
yarn add redux-flipper react-native-flipper
# for iOS
cd ios && pod install
```

2. Add the middleware into your redux store:

```javascript
import { createStore, applyMiddleware } from 'redux';

if (__DEV__) {
  const createDebugger = require('redux-flipper').default;

  let reduxDebugger = createDebugger();
  let store = createStore(RootReducer, {}, applyMiddleware(reduxDebugger));
} else {
  let store = createStore(RootReducer, {});
}
```

3. Install [flipper-plugin-redux-debugger](https://github.com/jk-gan/flipper-plugin-redux-debugger) in Flipper desktop client:

```
Manage Plugins > Install Plugins > search "redux-debugger" > Install
```

4. Start your app, then you should be able to see Redux Debugger on your Flipper app

## Acknowledgement

This plugin is inspired by [flipper-plugin-reduxinspector](https://github.com/blankapp/flipper-plugin-reduxinspector) which only for Flutter.

# Styling

React native does not use CSS for Styling - React Native không sử dụng css để Styling

You style your app using JavaScript - Bạn style cái app của bạn bằng các sử dụng JS

Names are written in camel case - tên phải là chữ viết lạc đà

ex: backgroundColor instead of background-color

Styling Approaches: cách tiếp cận styling

-   inline Styles

```js
// App.js
import { View } from "react-native";

export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum", padding: 60 }}>
            Hello World
        </View>
    );
}
```

-   StyleSheet API (StyleSheetAPI, style various core components, Styling across IOS and Android)

Tạo lời chào bằng cách custom View và Text

Tạo thư mục components

```js
// Greet.js
import { View, Text } from "react-native";

export default function Greet({ name }) {
    return {
        <View>
            <Text>Hello, {name}!</Text>
        </View>
    }
}
```

Nhận props là name truyền từ cha xuống con

```js
// app.js

import { View } from "react-native";
import Greet from "./components/Greet";

export default class App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum", padding: 60 }}>
            <Greet name="Bruce Wayne" />
            <Greet name="Clark Kent" />
        </View>
    )
}
```

Tái sử dụng code

Text

Component for displaying Text - Component dùng cho hiển thị chữ

It supports nesting, styling and touch handling - nó hỗ trợ cho việc lồng, styling và chạm vào

Depending on the target platform, React native will translate this component to either a UITextView ios a TextView android or p Web

Tùy thuộc vào mục tiêu của nền tảng, React Native sẽ dịch từ component sang UITextView IOS TextView android or p Web

Một ví dụ lỗi khi không dùng Text

```js
// App.js
import { View } from "react-native";

export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum" }}>Hello World</View>
    );
}
```

Text string must be recommended within a Text component

Lỗi ở đây View không chứa từ Hello World, cách khắc phụ là ta phải dùng Text để thể hiện được chữ

```js
// App.js
import { View, Text } from "react-native";

export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum" }}>
            <Text>Hello World</Text>
        </View>
    );
}
```

Thể hiện tính chất lồng của text ( cho 2 text lồng nhau)

```js
// App.js
import { View, Text } from "react-native";

export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum" }}>
            <Text>
                <Text style={{ color: "white" }}>Hello</Text> World
            </Text>
        </View>
    );
}
```

Tóm tắt để hiển thị văn bản trong reactnative chúng ta cần sử dụng Text, văn bản sẽ được Text bao bọc và chúng có thể lồng nhau.

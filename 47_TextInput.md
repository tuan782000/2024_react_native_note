# TextInput:

TextInput component is a fundamental building block for user input in React Native

It allows users to enter text and other data into your app

"Thành phần TextInput là một khối xây dựng cơ bản cho việc nhập liệu của người dùng trong React Native.

Nó cho phép người dùng nhập văn bản và dữ liệu khác vào ứng dụng của bạn."

```js
import {
    styleSheet,
    Text,
    View,
    StatusBar,
    SafeAreaView,
    TextInput,
} from "react-native";

import { useState } from "react";

export default function App() {
    const [name, setName] = useState("");
    return (
        <SafeAreaView style={styles.container}>
            <TextInput
                style={styles.input}
                value={name}
                onChangeText={setName}
            />
            <Text style={styles.text}>My name is {name}</Text>
        </SafeAreaView>
    );
}

const styles = StyleSheet.create({
    container: {
        flex: 1,
        backgroundColor: "#fff",
        paddingTop: StatusBar.currentHeight,
    },
    input: {
        height: 40,
        margin: 12,
        padding: 10,
        borderWidth: 1,
    },
    text: {
        fontSize: 30,
        padding: 10,
    },
});
```

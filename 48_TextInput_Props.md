# TextInput Props

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
                placeholder="email@example.com"
                autoCorrect={false}
                autoComplete="none"
                autoCapitalize="none"
                {/* secureTextEntity
                keyboardType="numeric" */}
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

mật khẩu thì thêm thuộc tính "secureTextEntity" để tăng tính bảo mật

Bật bàn phím là số bổ sung thuộc tính "keyboardType="numeric""

autoCorrect={false} Tắt chế độ chính tả

autoComplete="none" tắt chế độ tự động điền

autoCapitalize="none" tắt chế độ tự động viết hoa

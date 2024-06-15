# Multiline TextInput

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
            <TextInput style={[styles.input, styles.multilineText]} placeholder="message" multiline/>
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
    multilineText: {
        minHeight: 100,
        textAlignVertical: "top"
    }
});
```

Lưu ý TextInput có multiline thì bên android căn giữa nội dung nhập theo chiều dọc ô input. Cho nên để lên top, bổ sung thuộc tính textAlignVertical: "top" cho nó lên top

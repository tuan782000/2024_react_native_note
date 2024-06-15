# Switch

The Switch component serves as a valuable tool for integrating toggles into your app's user interface

It's particularly well-suited for scenarios where you require users to make binary choices, such as enabling or disabling specific app features

Thành phần Switch đóng vai trò là một công cụ quan trọng để tích hợp các công tắc vào giao diện người dùng của ứng dụng của bạn.

Nó đặc biệt thích hợp cho các tình huống khi bạn cần người dùng thực hiện các lựa chọn nhị phân, chẳng hạn như kích hoạt hoặc vô hiệu hóa các tính năng cụ thể của ứng dụng.

```js
import {
    styleSheet,
    Text,
    View,
    StatusBar,
    SafeAreaView,
    TextInput,
    Switch
} from "react-native";

import { useState } from "react";

export default function App() {
    const [name, setName] = useState("");
    const [isDarkMode, setIsDarkMode] = useState(false);
    return (
        <SafeAreaView style={[styles.container, { backgroundColor: isDarkMode ? "#000" : "#fff" }]}>
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
            <View style={styles.switchContainer}>
                <Text style={styles.text}>Dark Mode</Text>
                <Switch
                    value={isDarkMode}
                    onValueChange={() => setIsDarkMode((previousState) => !previousState)}
                    trackColor={{ false: "#767577", true: "lightblue" }}
                    thumbColor="#f4f3f4"
                />
            </View>
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
    },
    switchContainer: {
        flexDirection: "row",
        alignItems: 'center',
        justifyContent: "space-between",
        paddingHorizontal: 10,

    }
});
```

Thay đổi màu cho nút Switch

trackColor={{ false: "#767577", true: "lightblue" }} tắt sẽ là màu #767577, active thì light blue

thumbColor="#f4f3f4"

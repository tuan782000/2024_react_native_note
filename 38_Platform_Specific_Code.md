# Platform Specific Code

when devloping a cross-platform app, maximizing code reuse is a priority

There are situatuions where it becomes necessary to tailor your code specific platforms

React native offers two approaches for organizing and sperating platform-specific code

-   Platform module
-   Platform specific file extensions

Khi phát triển ứng dụng đa nền tảng, việc tối đa hóa việc sử dụng lại mã là một ưu tiên.

Có những tình huống khi cần điều chỉnh mã của bạn cho từng nền tảng cụ thể.

React Native cung cấp hai phương pháp để tổ chức và phân tách mã cụ thể cho từng nền tảng:

-   Mô-đun Platform
-   Phần mở rộng tệp cụ thể cho từng nền tảng

ex: paddingTop: Platform.OS === "android" ? 25 : 0,

chỉ những thằng android thì paddingTop 25, còn lại thì không có.

```js
import { StyleSheet, View, Text, SafeAreaView, Platform } from "react-native";
import CustomButton from "./components/CustomButton/CustomButton";

export default function App() {
    return (
        <SafeAreaView style={styles.safeContainer}>
            <View style={styles.container}>
                <View style={styles.box}>
                    <Text style={styles.text}>Welcome!</Text>
                    <CustomButton
                        title="Press me"
                        onPress={() => alert("Pressed!")}
                    />
                </View>
            </View>
        </SafeAreaView>
    );
}

const styles = StyleSheet.create({
    safeContainer: {
        flex: 1,
        backgroundColor: "plum",
    },
    container: {
        flex: 1,
        backgroundColor: "plum",
        alignItems: "center",
        justifyContent: "center",
        paddingTop: Platform.OS === "android" ? 25 : 0,
    },
    box: {
        width: windowWidth > 500 ? "70%" : "90%",
        height: windowHeight > 600 ? "60%" : "90%",
        backgroundColor: "lightblue",
        alignItems: "center",
        justifyContent: "center",
    },
    text: {
        ...Platform.select({
            ios: {
                color: "purple",
                fontSize: 24,
                fontStyle: "italic",
            },
            android: {
                color: "blue",
                fontSize: 30,
            },
        }),
        fontSize: windowWidth > 500 ? 50 : 24,
        fontWeight: "bold",
        textAlign: "center",
    },
});
```

components/CustomButton/CustomButton.ios.js

```js
import React from "react";
import { Pressable, Text } from "react-native";

const CustomButton = ({ onPress, title }) => {
    <Pressable
        onPress={onPress}
        style={{
            justifyContent: "center",
            alignItems: "center",
            backgroundColor: "lightblue",
            borderRadius: 20,
            padding: 10,
        }}
    >
        <Text style={{ color: "purple", fontSize: 18 }}>{title}</Text>
    </Pressable>;
};
```

components/CustomButton/CustomButton.android.js

```js
import React from "react";
import { Pressable, Text } from "react-native";

const CustomButton = ({ onPress, title }) => {
    <Pressable
        onPress={onPress}
        style={{
            justifyContent: "center",
            alignItems: "center",
            backgroundColor: "lightblue",
            borderRadius: 5,
            padding: 10,
        }}
    >
        <Text style={{ color: "blue", fontSize: 18 }}>{title}</Text>
    </Pressable>;
};
```

Tóm lại có 3 cách:

Platform.os

Platform.select

Nếu phức tạp hơn thì phân file chia component

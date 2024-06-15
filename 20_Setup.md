Tạo thư mục components

Box.js

```js
import { View, Text, StyleSheet } from "react-native";

export default function Box({ children, style }) {
    return (
        <View style={[styles.box, style]}>
            <Text style={styles.text}>{children}</Text>
        </View>
    );
}

const styles = StyleSheet.create({
    box: {
        backgroundColor: "#fff",
        padding: 20,
    },
    text: {
        fontSize: 24,
        fontWeight: "bold",
        textAlign: "center",
        color: "white",
    },
});
```

App.js (App sẽ truyền props cho Box nhận, thông qua children (Nội dung được bọc bởi Component Box) và style thuộc tính của component Box)

```js
import { View, StyleSheet } from "react-native";

export default function App() {
    return (
        <View style={styles.box}>
            <Box style={{ backgroundColor: "#8e9b00" }}>Box 1</Box>
            <Box style={{ backgroundColor: "#b65d1f" }}>Box 2</Box>
            <Box style={{ backgroundColor: "#1c4c56" }}>Box 3</Box>
            <Box style={{ backgroundColor: "#ab9156" }}>Box 4</Box>
            <Box style={{ backgroundColor: "#6b0803" }}>Box 5</Box>
            <Box style={{ backgroundColor: "#1c4c56" }}>Box 6</Box>
            <Box style={{ backgroundColor: "#b95f21" }}>Box 7</Box>
        </View>
    );
}

// không có marginTop thì IOS sẽ bị tai thỏ che mất chữ Box

const styles = StyleSheet.create({
    container: {
        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});
```

Ta thấy được container của ta thằng View có viền red cách top 64 và viền đó có độ dày là 6

Bên trong View là các Box, mỗi Box được xem là item của View Nội dùng và màu sắc được truyền từ cha App sang cho con Box

Đây là code chuẩn bị học flex box

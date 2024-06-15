alignContent

The alignContent property aligns lines of content along the cross axis

Similar to how the alignItems property aligns individual items along the cross axis

A very important condition is that multiple columns or rows must exist within the container

Thuộc tính alignContent căn chỉnh các dòng nội dung theo trục chéo.

Tương tự như cách thuộc tính alignItems căn chỉnh các phần tử riêng lẻ theo trục chéo.

Một điều rất quan trọng là cần phải có nhiều cột hoặc hàng trong container.

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
        height: 300,
        flexWrap: "wrap",
        alignContent: "flex-start", // nội dung các item con căn trái - đi từ trái sang phải
        alignContent: "flex-end", // nội dung các item con căn phải - đi từ trái sang phải
        alignContent: "center", // nội dung các item con căn giữa - đi từ trái sang phải
        alignContent: "stretch", // nội dung các item căn đều - kéo giản đều - và tự động xuống hàng
        alignContent: "space-between", // nội dung các item căn sát trái và phải, nhớ bổ sung width và height cho Box
        alignContent: "space-around", // khoảng các item gấp đôi khoảng cách item đến mép, nhớ bổ sung width và height cho Box
        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});
```

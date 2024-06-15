Gap related properties allow us to manage spacing between rows and columns

-   rowGap
-   columnGap
-   gap

Các thuộc tính liên quan đến khoảng cách giữa các hàng và cột cho phép chúng ta quản lý khoảng cách giữa chúng:

-   rowGap: Khoảng cách giữa các hàng.
-   columnGap: Khoảng cách giữa các cột.
-   gap: Khoảng cách giữa các hàng và cột (khi cả hai đều được áp dụng).

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
        {/* rowGap: Khoảng cách giữa các hàng. */}
        rowGap: 20,
        {/* columnGap: Khoảng cách giữa các cột. */}
        columnGap: 30,
        {/* chứa cả rowGap và columnGap */}
        gap: 10,
        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});
```

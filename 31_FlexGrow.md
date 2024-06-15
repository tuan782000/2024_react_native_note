FlexGrow

flexGrow determines how much space an item should occupy inside a flex container when there is extra space available

The flexGrow factor is always relative to other items within the container

Thuộc tính flexGrow xác định mức độ mà một phần tử nên chiếm không gian bên trong một container flex khi có không gian dư thừa có sẵn.

Yếu tố flexGrow luôn được tính toán dựa trên các phần tử khác bên trong container.

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
            <Box style={{ backgroundColor: "#6b0803", flexGrow: 1 }}>Box 5</Box>
            <Box style={{ backgroundColor: "#1c4c56", flexGrow: 1 }}>Box 6</Box>
            <Box style={{ backgroundColor: "#b95f21" }}>Box 7</Box>
        </View>
    );
}

// không có marginTop thì IOS sẽ bị tai thỏ che mất chữ Box

const styles = StyleSheet.create({
    container: {
        flex: 1,
        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});
```

flexGrow: 1 giúp cho Box 5 to hơn các Box khác

bổ sung cho Box 6 và lúc này Box 5 và Box ngang nhau và to hơn các Box khác

flexGrow: 1 Box 5

flexGrow: 3 Box 6

Lúc này Box 6 to gấp 3 lần Box 5

Mình có thể bổ sung trực tiếp flexGrow: 1 cho Component Box để các Box bằng nhau

flex vs flexGrow:

When flex is set to a positive number, it is equivalent to setting flexGrow with the same positive number

Khi thuộc tính flex được đặt thành một số dương, điều đó tương đương với việc đặt thuộc tính flexGrow với cùng một số dương đó.

flex also implicitly sets flexShrink to 1 and flexBasis to 0

Thuộc tính flex cũng ngầm định đặt flexShrink thành 1 và flexBasis thành 0.

```css
flex: <positive number>
flexGrow: `<positive number>`, flexShrink: 1, flexBasis: 0
``
```

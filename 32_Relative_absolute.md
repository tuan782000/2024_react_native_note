The layouts are based on the positon property, which defines how an element is positioned within its parent container

-   relative
-   absolute

Các bố cục được dựa trên thuộc tính position, nó xác định cách một phần tử được định vị trong container cha của nó.

Relative layout:

In this layout, an element is positioned according to the normal flow of the layout

It remains in its original position and can be offset from that positon using the top, right, bottom, and left values

Importanly, this offset does not affect the positioning of any sibling or parent elements.

Trong bố cục này, một phần tử được định vị theo luồng bình thường của bố cục.

Nó vẫn ở vị trí ban đầu của nó và có thể được lệch khỏi vị trí đó bằng cách sử dụng các giá trị top, right, bottom và left.

Quan trọng là, sự lệch này không ảnh hưởng đến việc định vị của bất kỳ phần tử chị em hoặc cha mẹ nào.

Absolute layout:

In this layout, an element does not participate in the normal flow of the layout

It is instead laid out independently of its siblings

The position of the element is determined by the top, right, bottom, and left values, which specify specific coordinates relative to its parent container.

Trong bố cục này, một phần tử không tham gia vào luồng bình thường của bố cục.

Thay vào đó, nó được bố trí một cách độc lập so với các phần tử chị em của nó.

Vị trí của phần tử được xác định bởi các giá trị top, right, bottom và left, chỉ định tọa độ cụ thể liên quan đến container cha của nó.

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
        width: 100,
        height: 100,
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
            <Box style={{ backgroundColor: "#8e9b00", top: 75, left: 75 }}>
                Box 1
            </Box>
            <Box style={{ backgroundColor: "#b65d1f" }}>Box 2</Box>
            <Box style={{ backgroundColor: "#1c4c56" }}>Box 3</Box>
            <Box
                style={{
                    backgroundColor: "#ab9156",
                    position: "absolute",
                    top: 100,
                    left: 100,
                }}
            >
                Box 4
            </Box>
            <Box style={{ backgroundColor: "#6b0803" }}>Box 5</Box>
            <Box style={{ backgroundColor: "#1c4c56" }}>Box 6</Box>
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

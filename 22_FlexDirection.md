Flex Direction

The FlexDirection property establishes the main axis, which is turn determines how the flex items are placed within the container

By default, the main axis flows from top to bottom, causing the items to be displayed from top to bottom in the UI

By changing the value of the FlexDirection property, we can alter how the item are positioned

Thuộc tính FlexDirection xác định trục chính, từ đó quyết định cách các phần tử flex được đặt trong container.

Mặc định, trục chính chảy từ trên xuống dưới, khiến cho các phần tử được hiển thị từ trên xuống dưới trong giao diện người dùng.

Bằng cách thay đổi giá trị của thuộc tính FlexDirection, chúng ta có thể thay đổi cách các phần tử được định vị.

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
        </View>
    );
}

// không có marginTop thì IOS sẽ bị tai thỏ che mất chữ Box

const styles = StyleSheet.create({
    container: {
        flex: 1,

        flexDirection: "column", // sẽ không có gì xảy ra vì nó đã ở trạng thái cột sẵn
        flexDirection: "column-reverse", // Box 3 lên đầu và Box 1 xuống cuối cùng, và vị trí bắt đầu đi từ dưới lên, chạm xuống đáy
        flexDirection: "row", // dạng hàng dọc xếp ngang, 3 cột này chiếm vừa với View thứ tự từ trái qua phải
        flexDirection: "row-reverse" // dạng hàng dọc xếp ngang, 3 cột này chiếm vừa với View thứ tự từ trái qua phải

        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});
```

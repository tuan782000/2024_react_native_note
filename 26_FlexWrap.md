Flex wrap allows us to control how flex items behave when there's limited space within the container

Flex wrap" cho phép chúng ta kiểm soát cách các phần tử flex hoạt động khi không gian bị hạn chế trong container.

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
        {/* Thay vì flex: 1 */}
        {/* Set chiều cao cho View, bạn sẽ thấy nội dung bị tràn ra khỏi thùng chứa */}
        height: 300,
        {/* có flexwrap 3 giá trị */}
        {/* giá trị mặc định, kết quả sẽ như ban đầu nội dung vẫn tràn ra */}
        flexWrap: 'nowrap',
        {/* wrap làm cho các phần tử bên trong nhỏ lại mất đi khả năng stretch và xuống hàng */}
        flexWrap: 'wrap',
        flexWrap: 'wrap-reverse',
        {/* đảo ngược */}
        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});

{/* ví dụ 2  */}
{/* View chiếm hết màn hình, các items sẽ mất stretch và nằm trên 1 hàng, nếu không đủ khoảng trống sẽ tự động xuống hàng */}
const styles = StyleSheet.create({
    container: {
        flex: 1,
        flexDirection: "row",
        flexWrap: 'wrap',
        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});
```

alignItems

alignItems defines the default behavior for laying out flex items along the container's cross-axis

Thuộc tính alignItems xác định hành vi mặc định cho việc bố trí các phần tử flex theo trục chéo của container.

Works similarly to justifyContent, but in the perpendicular direction - Hoạt động tương tự như justifyContent, nhưng ở hướng chéo tương phản.

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

const styles = StyleSheet.create({
    container: {
        flex: 1,
        // justifyContent: "flex-start", // mặc định flex-start sẵn Nội dung từ trên xuống dưới và bắt đầu đi từ top đi xuống
        alignItems: "stretch", // kéo dài ra chiếm hết. Nội dung mặc định
        alignItems: "flex-start", // nó chỉ hiển thị đẩy nội dùng đến khúc đầu cross - lưu ý nó không lắp đầy như stretch
        alignItems: "flex-end", // nó chỉ hiển thị đẩy nội dùng đến khúc cuối cross - lưu ý nó không lắp đầy như stretch
        alignItems: "flex-end", // nó chỉ hiển thị đẩy nội dùng đến khúc giữa cross - lưu ý nó không lắp đầy như stretch

        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});

const styles = StyleSheet.create({
    container: {
        flex: 1,
        flexDirection: "row",
        // justifyContent: "flex-start", // mặc định flex-start sẵn Nội dung từ trên xuống dưới và bắt đầu đi từ top đi xuống
        alignItems: "baseline", // canh nội dung theo đường cơ sở, không cần biết to nhỏ giữa các thực thể, nội dung sẽ được canh trên đường đó
        // Hãy thêm padding khác nhau, riêng cho các box để thấy sự khác biệt
        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});
```

JustifyContent

justifyContent defines the alignment along the main axis

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
        justifyContent: "flex-start", // mặc định flex-start sẵn Nội dung từ trên xuống dưới và bắt đầu đi từ top đi xuống
        justifyContent: "flex-end", // sẽ để ở cuối cùng nguyên khối đó sẽ ở cuối cùng chứ không riêng từng cái
        justifyContent: "center", // sẽ để ở canh giữa nguyên khối
        justifyContent: "space-between", // cách đều giữa các khối
        justifyContent: "space-around", // chia đều khoảng cách trái phải giữa các khối - 10 - | - 20 - | - 20 - | - 10 -
        justifyContent: "space-evenly", // chia đều mọi khoảng cách trái phải giữa các khối - 10 - | - 10 - | - 10 - | - 10 -
        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});

// or

const styles = StyleSheet.create({
    container: {
        flex: 1,
        flexDirection: "row",
        justifyContent: "flex-start", // mặc định flex-start sẵn Nội dung từ trên trái qua phải, chiều dọc chiếm hết theo flex
        justifyContent: "flex-end", // sẽ để nguyên khối ở bên phải, đó sẽ là nguyên khối  chứ không riêng từng cái
        justifyContent: "center", // sẽ để nguyên khối canh giữa, chiều dọc chiếm hết phần có thể chiếm
        justifyContent: "space-between", // cách đều giữa các khối
        justifyContent: "space-around", // chia đều khoảng cách trái phải giữa các khối - 10 - | - 20 - | - 20 - | - 10 -
        justifyContent: "space-evenly", // chia đều mọi khoảng cách trái phải giữa các khối - 10 - | - 10 - | - 10 - | - 10 -
        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});
```

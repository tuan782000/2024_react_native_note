Flex Shrink

flexShrink determines how children within a container shrink along the main axis when their combined size exceeds the container's size

The flexShrink factor is relative to other items within the container

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
            <Box style={{ backgroundColor: "#8e9b00", flexShrink: 1 }}>
                Box 1
            </Box>
            <Box style={{ backgroundColor: "#b65d1f", flexShrink: 1 }}>
                Box 2
            </Box>
        </View>
    );
}

// không có marginTop thì IOS sẽ bị tai thỏ che mất chữ Box

const styles = StyleSheet.create({
    container: {
        flex: 1,
        flexDirection: "row",
        alignItems: "flex-start",
        width: 300,
        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});
```

chiếm hết, các items cùng nằm trên 1 hàng, không wrap nên không xuống hàng được.
lúc này width chỉ còn 300, cho nên là Box 2 sẽ bị chồi ra ngoài. Khi bổ sung thêm flexShrink: 1 cho Box 2 thì Item Box 2 được co lại sao cho vừa với cha View

lúc này bổ sung vào cho Box 1 thì 2 cái nó sẽ co rút sao cho đều nhau nằm trọn vẹn trong View

```js
import { View, StyleSheet } from "react-native";

export default function App() {
    return (
        <View style={styles.box}>
            <Box style={{ backgroundColor: "#8e9b00", flexShrink: 1 }}>
                Box 1
            </Box>
            <Box style={{ backgroundColor: "#b65d1f", flexShrink: 2 }}>
                Box 2
            </Box>
        </View>
    );
}

// không có marginTop thì IOS sẽ bị tai thỏ che mất chữ Box

const styles = StyleSheet.create({
    container: {
        flex: 1,
        flexDirection: "row",
        alignItems: "flex-start",
        width: 300,
        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});
```

Box2 sẽ nhỏ hơn Box1 vì

flexShrink: 2 đã làm Box2 nhỏ hơn

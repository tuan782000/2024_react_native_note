AlignSelf

alignItems is applied to the container and controls the alignment of all items within it

alignSelf is applied to to individual items following us to control the alignment of each item independently

The values available for alignSelf are similar to those used in alignItems

alignItems được áp dụng cho container và điều khiển việc căn chỉnh của tất cả các phần tử bên trong nó.

alignSelf được áp dụng cho từng phần tử một cách độc lập, cho phép chúng ta kiểm soát căn chỉnh của mỗi phần tử một cách độc lập.

Các giá trị có sẵn cho alignSelf tương tự như những giá trị được sử dụng trong alignItems.

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
            <Box
                style={{ backgroundColor: "#8e9b00", alignSelf: "flex-start" }}
            >
                Box vẫn chiếm hết 1 hàng, nhưng nội dung chỉ chiếm phần đầu bên
                tay trái không stretch dài ra
            </Box>
            <Box style={{ backgroundColor: "#b65d1f", alignSelf: "flex-end" }}>
                Box vẫn chiếm hết 1 hàng, nhưng nội dung chỉ chiếm phần cuối bên
                tay phải không stretch dài ra
            </Box>
            <Box style={{ backgroundColor: "#1c4c56", alignSelf: "center" }}>
                Box vẫn chiếm hết 1 hàng, nhưng nội dung được căn ra giữa không
                stretch dài ra
            </Box>
            <Box style={{ backgroundColor: "#ab9156", alignSelf: "stretch" }}>
                Box chiếm hết 1 hàng, và kéo dài từ trái sang phải lấy hết
            </Box>
            <Box style={{ backgroundColor: "#6b0803" }}>Box 5</Box>
            <Box style={{ backgroundColor: "#1c4c56" }}>Box 6</Box>
            <Box style={{ backgroundColor: "#b95f21" }}>Box 7</Box>

            {/* Mặc dù Box 567 không có alignSelf nhưng mặc định alignSelf giá trị auto, alignSelf kế thừa từ alignItem mà mặc định alignItem là stretch cho nên auto sẽ lấy stretch
            
            Nếu thằng View có alignItems: flex-end, các thằng con alignSelf: auto sẽ tự động là alignSelf: flex-end
             */}
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

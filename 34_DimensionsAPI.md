Dimensions API

Dimensions.get('window') để lấy kích thước của cửa sổ hiển thị. Điều này thường được sử dụng để điều chỉnh giao diện của ứng dụng dựa trên kích thước màn hình của thiết bị.

```js
import { StyleSheet, View, Text, Dimensions } from "react-native";

export default function App() {
    return (
        <View style={styles.container}>
            <View style={styles.box}>
                <Text style={styles.text}>Welcome!</Text>
            </View>
        </View>
    );
}

const windowWidth = Dimensions.get("window").width;
const windowHeight = Dimensions.get("window").height;

const styles = StyleSheet.create({
    container: {
        flex: 1,
        backgroundColor: "plum",
        alignItems: "center",
        justifyContent: "center",
    },
    box: {
        width: windowWidth > 500 ? "70%" : "90%",
        height: windowHeight > 600 ? "60%" : "90%",
        backgroundColor: "lightblue",
        alignItems: "center",
        justifyContent: "center",
    },
    text: {
        fontSize: windowWidth > 500 ? 50 : 24,
    },
});
```

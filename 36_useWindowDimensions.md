# useWindowDimensions

đơn giản hóa bài 35

```js
import { StyleSheet, View, Text, useWindowDimensions } from "react-native";

export default function App() {
    const windowWidth = useWindowDimensions().width;
    const windowHeight = useWindowDimensions().height;
    return (
        <View style={styles.container}>
            <View style={styles.box}>
                <Text style={styles.text}>Welcome!</Text>
            </View>
        </View>
    );
}

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

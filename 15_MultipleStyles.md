```js
import { View, Text, StyleSheet } from "react-native";

export default function App() {
    return (
        <View style={styles.container}>
            <View style={styles.lightBlueBox}>
                <Text style={styles.title}>Light Blue Box</Text>
            </View>
            <View style={styles.lightGreenBox}>
                <Text style={styles.title}>Lightgreen Box</Text>
            </View>
        </View>
    );
}

{
    /* Nếu viết vầy thì trong file đó sử dụng được */
}
const styles = StyleSheet.create({
    container: { flex: 1, backgroundColor: "plum", padding: 60 },
    title: {},
    lightBlueBox: {
        backgroundColor: "lightblue",
        width: 100,
        height: 100,
        padding: 10,
    },
    lightGreenBox: {
        backgroundColor: "lightgreen",
        width: 100,
        height: 100,
        padding: 10,
    },
});
```

bị lặp code, khắc phục

Có nhiều hơn 1 style object thì đặt tất cả vào trong 1 mảng, thứ tự ưu tiên thì càng về cuối càng được ưu tiên

```js
import { View, Text, StyleSheet } from "react-native";

export default function App() {
    return (
        <View style={styles.container}>
            <View style={[styles.lightBlueBg, styles.box]}>
                <Text style={styles.title}>Light Blue Box</Text>
            </View>
            <View style={[styles.lightGreenBg, styles.box]}>
                <Text style={styles.title}>Lightgreen Box</Text>
            </View>
        </View>
    );
}

{
    /* Nếu viết vầy thì trong file đó sử dụng được */
}
const styles = StyleSheet.create({
    container: { flex: 1, backgroundColor: "plum", padding: 60 },
    title: {},
    box: {
         width: 100,
        height: 100,
        padding: 10,
    }
    lightBlueBg: {
        backgroundColor: "lightblue",
    },
    lightGreenBg: {
        backgroundColor: "lightgreen",
    },
});

```

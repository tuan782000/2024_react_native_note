Trong web có Box Model, điện thoại cũng có

Margin, border, padding, content

Marigin trái phải - MarginHorizontal

Margin trên dưới - MarginVertical

Tương tự

PaddingHorizontal

PaddingVertical

border: 2px solid purple; ở web hoạt động được như vầy

react native phải viết rõ ra

borderWidth: 2px,
borderColor: "purple",
borderStyle: "solid"

borderRadius nó sẽ không hoạt động trên Text của IOS, nhưng android thì có thể.

borderRadius hoạt động được trên View của cả 2 nên người ta sẽ khuyến khích dùng borderRadius cho View

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

const styles = StyleSheet.create({
    container: { flex: 1, backgroundColor: "plum", padding: 60 },
    title: {},
    box: {
        width: 100,
        height: 100,
        paddingHorizontal: 10,
        paddingVertical: 20,
        marginVertical: 10,
        borderWidth: 2,
        borderColor: "purple",
        borderRadius: 5
    }
    lightBlueBg: {
        backgroundColor: "lightblue",
    },
    lightGreenBg: {
        backgroundColor: "lightgreen",
    },
});
```

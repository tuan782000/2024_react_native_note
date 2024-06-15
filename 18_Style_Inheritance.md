# Style Inheritance

```js
import { View, Text, StyleSheet } from "react-native";

export default function App() {
    return (
        <View style={styles.container}>
            <View style={styles.darkMode}>
                <Text style={styles.darkModeText}>
                    Style inheritance{" "}
                    <Text style={styles.boldText}>in Bold</Text>
                </Text>
            </View>
            <View style={(styles.box, styles.lightBlueBg, styles.boxShadow)}>
                <Text style={styles.title}>Light Blue Box</Text>
            </View>
            <View
                style={(styles.box, styles.lightGreenBg, styles.androidShadow)}
            >
                <Text style={styles.title}>Lightgreen Box</Text>
            </View>
        </View>
    );
}

const styles = StyleSheet.create({
    container: { flex: 1, backgroundColor: "plum", padding: 60 },
    title: {},
    darkMode: {
        backgroundColor: "black",
    },
    darkModeText: {
        color: "white",
    },
    boldText: {
        fontWeight: "bold",
    },
    box: {
        width: 250,
        height: 250,
        paddingHorizontal: 10,
        paddingVertical: 20,
        marginVertical: 10,
        borderWidth: 2,
        borderColor: "purple",
        borderRadius: 5,
    },
    lightBlueBg: {
        backgroundColor: "lightblue",
    },
    lightGreenBg: {
        backgroundColor: "lightgreen",
    },
    boxShadow: {
        shadowColor: "#333333",
        shadowOffset: {
            width: 6,
            height: 6,
        },
        shadowOpacity: 0.6,
        shadowRadius: 4,
    },
    androidShadow: {
        elevation: 10,
    },
});
```

Bạn sẽ thấy View có back ground là màu đen, thằng con của nó View kế thừa đó và thành màu đen làm mất luôn chữ,
Sau khi thêm color white cho View thì Text không hề kế thừa vì trong reactnative hơi khác css bình thường.
Để đặt Text có chữ màu trắng buộc phải css cho Text

```js
<View style={styles.darkMode}>
    <Text>Style inheritance</Text>
</View>
```

Có ngoại lệ nếu 2 thành phần giống nhau thì vẫn có vụ kế thừa css cho nhau

```js
<View style={styles.darkMode}>
    <Text style={styles.darkModeText}>
        Style inheritance <Text style={styles.boldText}>in Bold</Text>
    </Text>
</View>
```

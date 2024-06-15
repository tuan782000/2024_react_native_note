Box Shadow

box-shadow: h-offset v-offset blur spread color

"h-offset": Độ lệch ngang của bóng đổ từ phần tử gốc.
"v-offset": Độ lệch dọc của bóng đổ từ phần tử gốc.
"blur": Độ mờ của bóng đổ.
"spread": Độ mở rộng của bóng đổ.
"color": Màu sắc của bóng đổ.

```js
import { View, Text, StyleSheet } from "react-native";

export default function App() {
    return (
        <View style={styles.container}>
            <View style={styles.box, styles.lightBlueBg, styles.boxShadow}>
                <Text style={styles.title}>Light Blue Box</Text>
            </View>
            <View style={styles.box, styles.lightGreenBg, styles.androidShadow}>
                <Text style={styles.title}>Lightgreen Box</Text>
            </View>
        </View>
    );
}

const styles = StyleSheet.create({
    container: { flex: 1, backgroundColor: "plum", padding: 60 },
    title: {},
    box: {
        width: 250,
        height: 250,
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
    boxShadow: {
        shadowColor: "#333333",
        shadowOffset: {
            width: 6,
            height: 6
        },
        shadowOpacity: 0.6,
        shadowRadius: 4
    },
    androidShadow: {
        elevation: 10
    }
});
```

Tuy nhiên IOS chịu thằng này, android lại không chịu thằng này

thằng android cung cấp thuộc tính elevation. Thuộc tính này làm boxshadow cho android

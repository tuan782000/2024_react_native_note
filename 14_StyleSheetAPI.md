# Style sheet API

```js
import { View, Text, StyleSheet } from "react-native";

export default function App() {
    return (
        <View style={styles.container}>
            <Text style={styles.title}>StyleSheet API</Text>
        </View>
    );
}

{
    /* Nếu viết vầy thì trong file đó sử dụng được */
}
const styles = StyleSheet.create({
    container: { flex: 1, backgroundColor: "plum", padding: 60 },
    title: {},
});

{
    /* Nhưng có từ khóa export các file khác có thể import vào dùng chung */
}
export const styles = StyleSheet.create({
    container: { flex: 1, backgroundColor: "plum", padding: 60 },
    title: {},
});
```

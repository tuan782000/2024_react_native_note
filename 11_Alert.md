# 11 Alert

Alert launches an alert dialog with specified title and message

"Alert khởi chạy một hộp thoại cảnh báo với tiêu đề và thông điệp cụ thể."

Optionally, you can also specify a list of buttons

Tùy chọn, bạn cũng có thể chỉ định một danh sách các nút

Truyền 1 tham số

```js
import { Alert, View, Button } from "react-native";
export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum", padding: 60 }}>
            <Button
                title="Alert"
                onPress={() => Alert.alert("Invalid data!")}
            />
        </View>
    );
}
```

Nhấn vào 1 hộp thoại show ra dialog

Nếu truyền 2 tham số

```js
import { Alert, View, Button } from "react-native";
export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum", padding: 60 }}>
            <Button
                title="Alert"
                onPress={() => Alert.alert("Invalid data!", "DOB incorrect")}
            />
        </View>
    );
}
```

Nếu truyền 3 tham số

```js
import { Alert, View, Button } from "react-native";
export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum", padding: 60 }}>
            <Button
                title="Alert"
                onPress={() =>
                    Alert.alert("Invalid data!", "DOB incorrect", [
                        {
                            text: "Cancel",
                            onPress: () => console.log("Cancel pressed"),
                        },
                        {
                            text: "OK",
                            onPress: () => console.log("OK pressed"),
                        },
                    ])
                }
            />
        </View>
    );
}
```

Show ra alert 3 tham số

-   tham số đầu sẽ là thông báo
-   tham số thứ hai là lỗi
-   tham số thứ 3 là các nút tương tác

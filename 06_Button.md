# Button

The button component allows users to trigger actions - button components cho phép người dùng phát đi hành động

The button component has platform-specific rendering for IOS and android - button components hiển thị cụ thể cho IOS và android

```js
// App.js
import { View, Button } from "react-native";
const logoImg = require("./assets/adaptive-icon.png");

export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum", padding: 60 }}>
            <Button>Submit</Button>

            <Button
                title="Press"
                onPress={() => {
                    console.log("Button Press");
                }}
                color="midnightblue"
            />
        </View>
    );
}
```

Lưu ý nhà Button hiển thị trên IOS và Android là hiển thị khác nhau

Trên web chúng ta có onClick để bắt sự kiện nhấn thì trên điện thoại có onPress để bắt sự kiện chạm vào màn hình

onPress là 1 prop

có các prop như color cung cấp màu sắc

prop vô hiệu hóa disabled - hay thường sử dụng trong form handling - khi thằng này xuất hiện nút đó sẽ bị vô hiệu hóa.

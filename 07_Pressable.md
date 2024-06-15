# Pressable

Pressable is a wrapper component that detects various stages of press interactions on its defined children

You can create a custom button using Pressable

-   onPressIn is called when a press is activated ( kích hoạt khi nhấn)
-   onLongPress is triggered when a press is held for longer than 500 milliseconds (giữ lâu sẽ phát sự kiện khi dữ lâu khoảng 0.5s) được kích hoạt khi một nhấn được giữ trong thời gian lâu hơn 500 mili giây.
-   onPressOut is called when a press gesture is deactivated ( được gọi khi một cử chỉ nhấn bị vô hiệu hóa.)
    "Pressable: cho phép nhấn"

Dùng Pressable là một phần tử bao bọc phát hiện các giai đoạn khác nhau của tương tác nhấn trên các phần tử con được xác định của nó.

```js
// App.js
import { View, Text, Image, ScrollView, Pressable } from "react-native";
const logoImg = require("./assets/adaptive-icon.png");

export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum", padding: 60 }}>
            <ScrollView>
                <Pressable
                    onPress={() => {
                        console.log("Press Image");
                    }}
                >
                    <Image
                        source={logoImg}
                        style={{ width: 300, height: 300 }}
                    />
                </Pressable>
                <Pressable
                    onPress={() => {
                        console.log("Press Text");
                    }}
                >
                    <Text>
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                        Phasellus at tristique turpis. Integer ut arcu ligula.
                        Duis sodales arcu eu arcu gravida, eget tincidunt lorem
                        condimentum. Vestibulum vel nisi id arcu dictum rhoncus
                        non ut sem. Vivamus euismod lacinia nunc, nec finibus
                        magna. Nunc nec turpis vel nisi vehicula commodo. Proin
                        fermentum lectus vitae ipsum facilisis, nec egestas
                        libero malesuada. Aenean in libero ac nulla aliquam
                        pulvinar. Fusce in arcu at sapien accumsan tristique.
                        Integer ut arcu ligula. Duis sodales arcu eu arcu
                        gravida, eget tincidunt lorem condimentum. Vestibulum
                        vel nisi id arcu dictum rhoncus non ut sem. Vivamus
                        euismod lacinia nunc, nec finibus magna.
                    </Text>
                </Pressable>
                <Image source={logoImg} style={{ width: 300, height: 300 }} />
            </ScrollView>
        </View>
    );
}
```

Để đặt sự kiện nhấn cho bất kỳ phần nào thì reactnative cung cấp Pressable, thằng này sẽ bọc các component cần bắt sự kiện nhấn. xem ví dụ ở trên.

Nếu bạn cảm thấy button chưa đủ thỏa mãn, bạn cũng có thể dựa vào Pressable để làm lại nút button mới

# Scroll View

```js
// App.js
import { View, Text, Image, ScrollView } from "react-native";
const logoImg = require("./assets/adaptive-icon.png");

export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum", padding: 60 }}>
            <ScrollView>
                <Image source={logoImg} style={{ width: 300, height: 300 }} />
                <Text>
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                    Phasellus at tristique turpis. Integer ut arcu ligula. Duis
                    sodales arcu eu arcu gravida, eget tincidunt lorem
                    condimentum. Vestibulum vel nisi id arcu dictum rhoncus non
                    ut sem. Vivamus euismod lacinia nunc, nec finibus magna.
                    Nunc nec turpis vel nisi vehicula commodo. Proin fermentum
                    lectus vitae ipsum facilisis, nec egestas libero malesuada.
                    Aenean in libero ac nulla aliquam pulvinar. Fusce in arcu at
                    sapien accumsan tristique. Integer ut arcu ligula. Duis
                    sodales arcu eu arcu gravida, eget tincidunt lorem
                    condimentum. Vestibulum vel nisi id arcu dictum rhoncus non
                    ut sem. Vivamus euismod lacinia nunc, nec finibus magna.
                </Text>
                <Image source={logoImg} style={{ width: 300, height: 300 }} />
            </ScrollView>
        </View>
    );
}
```

Nội dung bên trong này đã dài quá màn hình, và phần Image cuối đã chị che mất. Người dùng muốn xem hình bên dưới nhưng không xem được

React native cung cấp cho ta 1 component ScrollView

ScrollView component wraps the platform-specific scrolling functionality - ScrollView component bọc toàn bộ nền tảng trong cuộn chức năng

SrcollView require a bounded height to function properly - ScrollView yêu cầu giới hạn chiều cao để hoạt động tốt

View ngoài đóng vai trò như 1 cái giới hạn chiều cao - cách status bar ra 60

Scroll view lúc nào cũng là con của View nhưng lại là cha của toàn bộ thông tin bên trong nên cuộn được hết các thông tin bên trong

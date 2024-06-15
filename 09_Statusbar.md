# Status bar:

The StatusBar component allows you to control the application's status bar (thanh này nằm ngoài màn hình)

Thành phần StatusBar cho phép bạn kiểm soát thanh trạng thái của ứng dụng.

The status bar is the zone, typically at the top of the screen, that displays the current time, wifi, and network information, battery level other staus icon.

Thanh trạng thái là vùng, thường ở đầu màn hình, hiển thị thời gian hiện tại, tín hiệu wifi và mạng, mức pin và các biểu tượng trạng thái khác.

```js
// App.js
import { View } from "react-native";

export default function App() {
    return <View style={{ flex: 1, backgroundColor: "plum" }}></View>;
}
```

Chưa có component StatusBar thì View chiếm luôn phần status bar, nội dung status bar nằm đè lên view

```js
// App.js
import { View, StatusBar } from "react-native";

export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum" }}>
            <StatusBar />
        </View>
    );
}
```

Thì IOS không có gì thay đổi

Android thì phần status bar nó được làm nổi màu đen lên

```js
// App.js
import { View, StatusBar } from "react-native";

export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum" }}>
            <StatusBar backgroundColor="lightgreen" barStyle="default" />
        </View>
    );
}
```

IOS không có gì xảy ra nhưng andorid thì chuyển đổi màu

barStyle IOS chữ đen còn Android chữ màu trắng

barStyle="dark-content" thì ios và android chữ màu đen

barStyle="white-content" thì ios và android chữ màu trắng

Nếu thêm prop hidden cho StatusBar thì sẽ ẩn đi

# Image

The image component enables us to display various types of images including

image components cho phép chúng tôi hiển thị nhiều loại hình ảnh

-   static image
-   network images
-   images from the local disk, such as the camera roll - hình ảnh từ ổ đĩa, chẳng hạn ảnh camera

React native seamlessly translates the image component to platform-specific counterparts:

-   UIImageView for IOS
-   ImageView for Android
-   img for web
    React Native tự động dịch thành phần hình ảnh thành các phiên bản cụ thể cho từng nền tảng một cách mượt mà:

```js
// App.js
import { View, Text, Image } from "react-native";
const logoImg = require("./assets/adaptive-icon.png");

export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum" }}>
            <Image source={logoImg} style={{ width: 300, height: 300 }} />
            <Image
                source={{ uri: "https://picsum.photos/300" }}
                style={{ width: 300, height: 300 }}
            />
        </View>
    );
}
```

Thuộc tính source của thành phần Image trong React Native nhận vào một đối tượng định nghĩa nguồn của hình ảnh.

source nhận đối tượng không nhận chuỗi hoặc số,...

# Image background

```js
// App.js
import { View, Text, ImageBackground } from "react-native";
const logoImg = require("./assets/adaptive-icon.png");

export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum" }}>
            <ImageBackground source={logoImg} style={{ flex: 1 }}>
                <Text>IMAGE TEXT</Text>
            </ImageBackground>
        </View>
    );
}
```

Chúng ta thấy được hình ảnh nằm dưới, chữ nằm trên ảnh

ImageBackground có flex: 1 nó sẽ tự động mở rộng sao cho chiếm hết không gian có sẵn

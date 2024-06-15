Dynamic User Interfaces

Currently, all our learning has centered around iPhone 14 and Pixel 4 devices

Our app's users won't all be using identical devices

Devices sizes may vary, ranging from more compact phones to larger devices like Ipads or Adnroid tablets

we must ensure that our app's user interface remains responsive to these different devices sizes while maintaining an optiomal user experience

On the same device, a user might opt for portrait mode while another prefers landscape orientation

Hiện tại, tất cả việc học của chúng ta đã tập trung vào các thiết bị iPhone 14 và Pixel 4.

Tuy nhiên, người dùng của ứng dụng của chúng ta sẽ không sử dụng cùng loại thiết bị.

Kích thước của các thiết bị có thể thay đổi, từ các điện thoại nhỏ gọn hơn đến các thiết bị lớn hơn như iPad hoặc tablet chạy Android.

Chúng ta phải đảm bảo rằng giao diện người dùng của ứng dụng của chúng ta vẫn linh hoạt đối với các kích thước thiết bị khác nhau trong khi vẫn duy trì một trải nghiệm người dùng tối ưu.

Trên cùng một thiết bị, một người dùng có thể chọn chế độ dọc trong khi người dùng khác lại thích hướng ngang.

```js
import { StyleSheet, View } from "react-native";

export default function App() {
    return <View style={styles.container}></View>;
}

const styles = StyleSheet.create({
    container: {
        flex: 1,
        backgroundColor: "plum",
        alignItems: "center",
        justifyContent: "center",
    },
});
```

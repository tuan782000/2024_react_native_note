Stack Navigation

Each new screen is stacked on top of the previous one like a deck of cards

Mỗi màn hình mới được xếp chồng lên trên màn hình trước đó giống như một bộ bài.

When you navigate to a new screen, a new card is placed on top of the stack, and when you navigate back, the top card is removed, revealing the previous screen

Khi bạn điều hướng đến một màn hình mới, một thẻ mới được đặt lên đỉnh của ngăn xếp, và khi bạn điều hướng quay lại, thẻ trên cùng được loại bỏ, hiển thị màn hình trước đó.

Allows users to drill down into detailed views and then retrace their steps when done

Cho phép người dùng đi sâu vào các chế độ xem chi tiết và sau đó làm lại các bước của họ khi hoàn thành

It's particularly useful in scenarios where a linear flow of screen is required

"Nó đặc biệt hữu ích trong các kịch bản mà luồng màn hình theo trình tự cần thiết."

List View to Details View to More Details View

"Chế độ xem danh sách đến chế độ xem chi tiết đến chế độ xem chi tiết hơn."

Two navigators: Stack Navigatior and Native Stack Navigatior

The Stack Navigatior is a javascript-based navigator which offers a high degree of customization, making it a great choice for apps that require a unique navigation experience

"The Stack Navigator là một trình điều hướng dựa trên JavaScript cung cấp một mức độ tùy chỉnh cao, làm cho nó trở thành lựa chọn tuyệt vời cho các ứng dụng yêu cầu một trải nghiệm điều hướng độc đáo."

However, this comes at the cost of performance especially when compared to its counterpart, the Native Stack Navigator

"Tuy nhiên, điều này đi kèm với chi phí về hiệu suất đặc biệt là khi so sánh với phiên bản của nó, Native Stack Navigator."

The native stack navigator leverages the native navigation constructors of IOS and Android, providing better performance and a more native feel to the transitions and gestures

"Native Stack Navigator tận dụng các hàm tạo điều hướng cục bộ của IOS và Android, cung cấp hiệu suất tốt hơn và cảm giác gần gũi hơn với các chuyển động và cử chỉ cục bộ."

The caveat here is, it might not offer the same level of customization as the stack navigatior

"Nhược điểm ở đây là, nó có thể không cung cấp cùng mức độ tùy chỉnh như Stack Navigator."

npm install @react-navigation/native-stack

App.js

```js
import { NavigationContainer } from "@react-navigation/native";
import { createNativeStackNavigator } from "@react-navigation/native-stack";
import HomeScreen from "./screens/HomeScreen";
import AboutScreen from "./screens/AboutScreen";

const Stack = createNativeStackNavigator();

export default function App() {
    return (
        <NavigationContainer>
            <Stack.Navigator initialRouteName="">
                <Stack.Screen name="Home" component={HomeScreen} />
                <Stack.Screen name="About" component={AboutScreen} />
            </Stack.Navigator>
        </NavigationContainer>
    );
}
```

name="" sẽ là tiêu đề của lá bài đó IOS thì center còn android thì nằm bên tay trái

initialRouteName="" thuộc tính này là set trang nào là mặc định đầu tiên sẽ xuất hiện

Tạo Thư mục screens/HomeScreen.js

```js
import React from "react";
import { View, Text, Button, StyleSheet } from "react-native";

export default function HomeScreen() {
    return (
        <View style={styles.container}>
            <Text style={styles.text}>Home Screen</Text>
        </View>
    );
}

const styles = StyleSheet.create({
    container: {
        flex: 1,
        alignItems: "center",
        justifyContent: "center",
    },
    text: {
        fontSize: 24,
        fontWeight: "bold",
        marginBottom: 16,
    },
});
```

AboutScreen.js

```js
import React from "react";
import { View, Text, Button, StyleSheet } from "react-native";

export default function AboutScreen() {
    return (
        <View style={styles.container}>
            <Text style={styles.text}>About Screen</Text>
        </View>
    );
}

const styles = StyleSheet.create({
    container: {
        flex: 1,
        alignItems: "center",
        justifyContent: "center",
    },
    text: {
        fontSize: 24,
        fontWeight: "bold",
        marginBottom: 16,
    },
});
```

# Navigation

The mechanism that allows users to move across different screens, access features, and generally use your app effectively

A go to solution for handling navigation is the React Navigation library

Expo has its own built-in routing feature exclusive to Expo projects

React navigation works both with and without Expo in React native Apps

Focus on React navigation in this section.

Cơ chế cho phép người dùng di chuyển qua các màn hình khác nhau, truy cập tính năng và sử dụng ứng dụng của bạn một cách hiệu quả chung.

Một giải pháp phổ biến để xử lý điều hướng là thư viện React Navigation.

Expo có cơ chết routing riêng nhưng chỉ phục vụ cho dự án React native Expo

React navigation thì hoạt động cả trên expo và react native cli

Tập trung vào react navigation trong phần này

# React Navigation:

Provides a variety of navigatiors like Stack, Drawer, and Tab navigatior

Stack Navigatior provides a way for your app to transition between screens where each new screen is placed on to of a stack

Drawer Navigatior renders a navigation drawer on the side of the screen which can be opened and closed via gestures

A tab navigatior at the bottom of your screen lets you easily switch between different routes

"Cung cấp nhiều bộ điều hướng giống như: Stack, Drawer, and Tab navigatior"

"Stack Navigator cung cấp một cách cho ứng dụng của bạn chuyển đổi giữa các màn hình, trong đó mỗi màn hình mới được đặt lên đỉnh của một ngăn xếp."

"Drawer Navigator render một ngăn kéo điều hướng ở bên cạnh màn hình có thể mở và đóng bằng cử chỉ."

"Một tab navigator ở dưới cùng của màn hình cho phép bạn dễ dàng chuyển đổi giữa các tuyến đường khác nhau."

Cách để cấu hình vào dự án:

npm install @react-navigation/native

npx expo install react-native-screens react-native-safe-area-context

Để hoạt động chính xác NavigationContainer bọc nguyên dự án của chúng ta

App.js

```js
import { NavigationContainer } from "@react-navigation/native";

export default function App() {
    return (
        <NavigationContainer>{/* Rest of your app code */}</NavigationContainer>
    );
}
```

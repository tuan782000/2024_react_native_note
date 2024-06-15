React native có thể dùng: expo hoặc react native cli

expo sẽ phù hợp hơn cho những người mới bắt đầu, phù hợp cho dự án nhỏ và vừa

react native cli phù hợp cho việc phát triển dự án vừa và lớn

# 1 Expo:

npx create-expo-app@latest ten_du_an

npx create-expo-app@latest HelloWorld

package.json

chứa các thông tin dự án

scripts và dependencies (expo, react, react-native,...) và devdependencies

babel.config.js

nó là cấu hình

app.json: quan trọng, chứa các tùy chọn cho dự án

App.js sẽ là thứ được đọc và hiển thị lên màn hình dự án

# 2 Câu lệnh chạy:

cd vào dự án

-   npm run android (chạy cho dự án android)
-   npm run ios (chạy cho dự án ios)
-   npm run web

nhấn: npm start

nó sẽ sinh ra 1 QR code dùng điện thoại(có ứng dụng expo)

Và đảm bảo rằng máy tính và điện thoại kết nối chung 1 mạng

quét mã vạch đó

# 3 Core components:

when we use React create web user interfaces, we often utilize HTML tags such as div, span and paragraph

In Android and IOS development, we employ a fundamental building block called view for user interfaces

A view is small rectangular element on the screen that can display text, images, or respond to user input

Android views are written in java-kotlin
IOS views are written in swift - objective-C

React-native views using javascript through React components

At runtime, React native generates the corresponding android and ios views for these components

React native offers a collection of essential pre-built components knows as "Core components" which are readily for building your native app's user interface

-   React Native UI components: View, Text, Image, ScrollView, TextInput
-   Android View: ViewGroup, TextView, ImageView, ScrollView, EditText
-   IOS View: UIView, UITextView, UIImageView, UIScrollView, UITextField
-   Web: div, p, img, div, input

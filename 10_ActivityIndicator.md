# 10. Activity Indicator

The ActivityIndicator component displays a circular loading indicator

Thành phần ActivityIndicator hiển thị một chỉ báo vòng tròn đang tải.

It is used to inform users about the status of ongoing processes, such as loading an app, submitting a form, or saving updates

Nó được sử dụng để thông báo cho người dùng về trạng thái của các quy trình đang diễn ra, như tải ứng dụng, gửi biểu mẫu, hoặc lưu các cập nhật.

```js
// App.js
import { View, ActivityIndicator } from "react-native";

export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum", padding: 60 }}>
            <ActivityIndicator />
            <ActivityIndicator size="small" />
            <ActivityIndicator size="large" />
            <ActivityIndicator size="large" color="midnightblue" />
            <ActivityIndicator
                size="large"
                color="midnightblue"
                animating={false}
            />
        </View>
    );
}
```

Bài tập

```js
// App.js
import { View, ActivityIndicator, Button } from "react-native";
import { useState } from "react";

export default function App() {
    const [loading, setLoading] = useState(false);

    return (
        <View style={{ flex: 1, backgroundColor: "plum", padding: 60 }}>
            <Button onPress={() => setLoading(!loading)}>Show Loading</Button>
            <ActivityIndicator
                size="large"
                color="midnightblue"
                animating={loading}
            />
        </View>
    );
}
```

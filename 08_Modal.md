# Modal

Modal is a screen that overlays the app content to provide important information or prompt the user for a decision.

Modal là một màn hình nằm trên cùng của nội dung ứng dụng để cung cấp thông tin quan trọng hoặc yêu cầu người dùng ra quyết định.

Since they are purposefully interruptive make sure you use them only when necessary: "Vì chúng làm gián đoạn một cách có chủ đích, hãy đảm bảo bạn chỉ sử dụng chúng khi cần thiết."

```js
// App.js
import { useState } from "React";
import { View, Button, Text, Modal } from "react-native";

export default function App() {
    const [isModalVisible, setIsModalVisible] = useState(false);
    return (
        <View style={{ flex: 1, backgroundColor: "plum", padding: 60 }}>
            <Button
                title="Press"
                onPress={() => setIsModalVisible(!isModalVisible)}
                color="midnightblue"
            />

            <Modal visible={isModalVisible}>
                <View
                    style={{
                        flex: 1,
                        backgroundColor: "lightblue",
                        padding: 60,
                    }}
                >
                    <Text>Modal Content</Text>
                    <Button
                        title="Close"
                        color="midnightblue"
                        onPress={() => setIsModalVisible(!isModalVisible)}
                    />
                </View>
            </Modal>
        </View>
    );
}
```

có thể đặt onRequestClose vào trong Modal để làm tính năng chạm vào khoảng không để đóng Modal lại

```js
<Modal
    visible={modalVisible}
    onRequestClose={() => {
        // Xử lý khi Modal đóng lại
    }}
>
    {/* Nội dung Modal */}
</Modal>
```

IOS còn cung cấp cho 2 thuộc tính animationType và presentationStyle, android thì không có 2 thuộc tính này

animationType="slide"
animationType="fade"
presentationStyle="pageSheet"
presentationStyle="formSheet"
presentationStyle="fullscreen"

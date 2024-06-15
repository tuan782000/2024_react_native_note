Flex react native

cross: trục ngang từ trái sang phải

main: trục dọc từ trên xuống dưới

Ngược lại so với trục của web

The flex property plays a crucial role in definding how much of a view fill the screen along the main axis.

Thuộc tính "flex" đóng vai trò quan trọng trong việc xác định mức độ mà một view chiếm màn hình theo trục chính.

It accepts an integer value greater than or equal to 0, indicating the fraction of the available space the component should occupy.

Nó chấp nhận một giá trị số nguyên lớn hơn hoặc bằng 0, chỉ ra phần trăm của không gian có sẵn mà thành phần nên chiếm.

trong React Native, mặc định của thành phần View là sử dụng display: flex.

Điều này có nghĩa khi bạn sử dụng View mà không định nghĩa display cho View đó thì mặc định nó sẽ lấy display: flex;

Nhớ lại ví dụ, làm background cho màn hình View

Mặc dù View có backgroundColor nhưng màn hình vẫn trắng. Vì View nó đang chiếm đến phần nó được chiếm, vì hiện tại nó không chiếm cho nên có đặt backgroundColor thì vẫn không hiển thị màu nền

```js
// App.js
import { View } from "react-native";

export default function App() {
    return <View style={{ backgroundColor: "plum" }}></View>;
}
```

Nhưng mặc định View là display: flex, cho nên có thể dùng flex: 1 để View đó chiếm được hết phần nó có thể chiếm

```js
// App.js
import { View } from "react-native";

export default function App() {
    return <View style={{ flex: 1, backgroundColor: "plum" }}></View>;
}
```

---

```js
import { View, Text, StyleSheet } from "react-native";

export default function Box({ children, style }) {
    return (
        <View style={[styles.box, style]}>
            <Text style={styles.text}>{children}</Text>
        </View>
    );
}

const styles = StyleSheet.create({
    box: {
        backgroundColor: "#fff",
        padding: 20,
    },
    text: {
        fontSize: 24,
        fontWeight: "bold",
        textAlign: "center",
        color: "white",
    },
});
```

App.js (App sẽ truyền props cho Box nhận, thông qua children (Nội dung được bọc bởi Component Box) và style thuộc tính của component Box)

```js
import { View, StyleSheet } from "react-native";

export default function App() {
    return (
        <View style={styles.box}>
            <Box style={{ backgroundColor: "#8e9b00" }}>Box 1</Box>
            <Box style={{ backgroundColor: "#b65d1f" }}>Box 2</Box>
            <Box style={{ backgroundColor: "#1c4c56" }}>Box 3</Box>
            <Box style={{ backgroundColor: "#ab9156" }}>Box 4</Box>
            <Box style={{ backgroundColor: "#6b0803" }}>Box 5</Box>
            <Box style={{ backgroundColor: "#1c4c56" }}>Box 6</Box>
            <Box style={{ backgroundColor: "#b95f21" }}>Box 7</Box>
        </View>
    );
}

// không có marginTop thì IOS sẽ bị tai thỏ che mất chữ Box

const styles = StyleSheet.create({
    container: {
        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});
```

Ở View này, bạn thấy View này nó chiếm bằng tổng các thằng con nằm trong nó

```js
import { View, Text, StyleSheet } from "react-native";

export default function Box({ children, style }) {
    return (
        <View style={[styles.box, style]}>
            <Text style={styles.text}>{children}</Text>
        </View>
    );
}

const styles = StyleSheet.create({
    box: {
        backgroundColor: "#fff",
        padding: 20,
    },
    text: {
        fontSize: 24,
        fontWeight: "bold",
        textAlign: "center",
        color: "white",
    },
});
```

App.js (App sẽ truyền props cho Box nhận, thông qua children (Nội dung được bọc bởi Component Box) và style thuộc tính của component Box)

```js
import { View, StyleSheet } from "react-native";

export default function App() {
    return (
        <View style={styles.box}>
            <Box style={{ backgroundColor: "#8e9b00" }}>Box 1</Box>
            <Box style={{ backgroundColor: "#b65d1f" }}>Box 2</Box>
            <Box style={{ backgroundColor: "#1c4c56" }}>Box 3</Box>
            <Box style={{ backgroundColor: "#ab9156" }}>Box 4</Box>
            <Box style={{ backgroundColor: "#6b0803" }}>Box 5</Box>
            <Box style={{ backgroundColor: "#1c4c56" }}>Box 6</Box>
            <Box style={{ backgroundColor: "#b95f21" }}>Box 7</Box>
        </View>
    );
}

// không có marginTop thì IOS sẽ bị tai thỏ che mất chữ Box

const styles = StyleSheet.create({
    container: {
        flex: 1,
        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});
```

Nhưng bây giờ tôi muốn View tự quyết định chiều cao cho nó không phụ thuộc vào các Box, bằng cách bổ sung flex: 1

Lúc này container này sẽ chiếm hết màn hình

Ví dụ tiếp theo

```js
import { View, Text, StyleSheet } from "react-native";

export default function Box({ children, style }) {
    return (
        <View style={[styles.box, style]}>
            <Text style={styles.text}>{children}</Text>
        </View>
    );
}

const styles = StyleSheet.create({
    box: {
        backgroundColor: "#fff",
        padding: 20,
    },
    text: {
        fontSize: 24,
        fontWeight: "bold",
        textAlign: "center",
        color: "white",
    },
});
```

App.js (App sẽ truyền props cho Box nhận, thông qua children (Nội dung được bọc bởi Component Box) và style thuộc tính của component Box)

```js
import { View, StyleSheet } from "react-native";

export default function App() {
    return (
        <View style={styles.box}>
            <Box style={{ backgroundColor: "#8e9b00", flex: 1 }}>Box 1</Box>
            <Box style={{ backgroundColor: "#b65d1f" }}>Box 2</Box>
            <Box style={{ backgroundColor: "#1c4c56" }}>Box 3</Box>
            <Box style={{ backgroundColor: "#ab9156" }}>Box 4</Box>
            <Box style={{ backgroundColor: "#6b0803" }}>Box 5</Box>
            <Box style={{ backgroundColor: "#1c4c56" }}>Box 6</Box>
            <Box style={{ backgroundColor: "#b95f21" }}>Box 7</Box>
        </View>
    );
}

// không có marginTop thì IOS sẽ bị tai thỏ che mất chữ Box

const styles = StyleSheet.create({
    container: {
        flex: 1,
        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});
```

Thằng Box 1 sẽ to hơn những thằng Box còn lại vì nó được quyền chiếm các phần dư còn lại, các Box khác thì không, nhưng nếu số lượng Box quá nhiều chiếm hết không gian trống thì lúc này Box 1 sẽ nhỏ hơn các Box khác

Nếu các có nhiều hơn 1 Item sở hữu flex 1, thì các khoảng trống đều được chia đều với nhau

```js
import { View, Text, StyleSheet } from "react-native";

export default function Box({ children, style }) {
    return (
        <View style={[styles.box, style]}>
            <Text style={styles.text}>{children}</Text>
        </View>
    );
}

const styles = StyleSheet.create({
    box: {
        backgroundColor: "#fff",
        padding: 20,
    },
    text: {
        fontSize: 24,
        fontWeight: "bold",
        textAlign: "center",
        color: "white",
    },
});
```

App.js (App sẽ truyền props cho Box nhận, thông qua children (Nội dung được bọc bởi Component Box) và style thuộc tính của component Box)

```js
import { View, StyleSheet } from "react-native";

export default function App() {
    return (
        <View style={styles.box}>
            <Box style={{ backgroundColor: "#8e9b00", flex: 1 }}>Box 1</Box>
            <Box style={{ backgroundColor: "#b65d1f", flex: 3 }}>Box 2</Box>
            <Box style={{ backgroundColor: "#1c4c56" }}>Box 3</Box>
            <Box style={{ backgroundColor: "#ab9156" }}>Box 4</Box>
            <Box style={{ backgroundColor: "#6b0803" }}>Box 5</Box>
            <Box style={{ backgroundColor: "#1c4c56" }}>Box 6</Box>
            <Box style={{ backgroundColor: "#b95f21" }}>Box 7</Box>
        </View>
    );
}

// không có marginTop thì IOS sẽ bị tai thỏ che mất chữ Box

const styles = StyleSheet.create({
    container: {
        flex: 1,
        marginTop: 64,
        borderWidth: 6,
        borderColor: "red",
    },
});
```

Lúc này tỷ lệ flex đã khác, 1 và 3 chỉ theo tỷ lệ Box1 = 1/3 Box3

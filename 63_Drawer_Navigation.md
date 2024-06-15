# Drawer Navigation

Drawer navigator introduces a hidden menu, sliding from either side of the screen

It is particularly beneficial in apps with multiple main sections that require a neat an organized navigation structure

"Drawer Navigator giới thiệu một menu ẩn, trượt từ một trong hai bên của màn hình.

Nó đặc biệt hữu ích trong các ứng dụng có nhiều phần chính yêu cầu một cấu trúc điều hướng sạch sẽ và có tổ chức."

Cài đặt cho dự án

npm install @react-navigation/drawer

cài thêm 2 thằng react-native-gesture-handler và react-native-reanimated

npx expo install react-native-gesture-handler react-native-reanimated

App.js

```js
import "react-native-gesture-handler";
import { NavigationContainer } from "@react-navigation/native";
import { createDrawerNavigator } from "@react-navigation/drawer";

const Drawer = createDrawerNavigator();

export default function App() {
    return (
        <NavigationContainer>
            <Drawer.Navigator>
                <Drawer.Screen name="Dashboard" component={DashboardScreen} />
                <Drawer.Screen name="Settings" component={SettingScreen} />
            </Drawer.Navigator>
        </NavigationContainer>
    );
}
```

AppStack.js

```js
import { NavigationContainer } from "@react-navigation/native";
import { createNativeStackNavigator } from "@react-navigation/native-stack";
import HomeScreen from "./screens/HomeScreen";
import AboutScreen from "./screens/AboutScreen";
import { Pressable } from "react-native";

const Stack = createNativeStackNavigator();

export default function App() {
    return (
        <NavigationContainer>
            <Stack.Navigator
                initialRouteName="Home"
                screenOptions={{
                    headerStyle: { backgroundColor: "#6a51ae" },
                    headerTintColor: "#fff",
                    headerTitleStyle: { fontWeight: "bold" },
                    headerRight: () => (
                        <Pressable
                            onPress={() => alert("Menu button pressed!!!")}
                        >
                            <Text style={{ color: "#fff", fontSize: 16 }}>
                                Menu
                            </Text>
                        </Pressable>
                    ),
                    contentStyle: {
                        backgroundColor: "#e8e4f3",
                    },
                }}
            >
                <Stack.Screen
                    name="Home"
                    component={HomeScreen}
                    options={{
                        title: "Welcome Home",
                    }}
                />
                <Stack.Screen
                    name="About"
                    component={AboutScreen}
                    initialParams={{ name: "Guest" }}
                    options={({ route }) => ({
                        title: route.params.name,
                    })}
                />
            </Stack.Navigator>
        </NavigationContainer>
    );
}
```

Tạo Thư mục screens/HomeScreen.js

```js
import React from "react";
import { View, Text, Button, StyleSheet, Button } from "react-native";
import { useNavigation } from "@react-navigation/native";

export default function HomeScreen({ navigation, route }) {
    const navigation = useNavigation();
    return (
        <View style={styles.container}>
            <Text style={styles.text}>Home Screen</Text>
            <Text style={styles.text}>{route.params?.result}</Text>
            <Button
                title="Go to About"
                onPress={() => navigation.navigate("About")}
            />
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

export default function AboutScreen({ route, navigation }) {
    const { name } = route.params;
    return (
        <View style={styles.container}>
            <Text style={styles.text}>About Screen {name}</Text>
            <Button
                title="Update the name"
                onPress={() =>
                    navigation.setParams({
                        name: "Codevolution",
                    })
                }
            />
            <Button
                title="Go back with data"
                onPress={() =>
                    navigation.navigate("Home", { result: "Data from about" })
                }
            />
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

Chỉnh sửa babel.config.js

```js
module.exports = function (api) {
    api.cache(true);
    return {
        presets: ["babel-preset-expo"],
        plugins: ["react-native-reanimated/plugin"],
    };
};
```

npx expo start -c

"start": "expo start -c"

DashboardScreen.js

```js
import { StyleSheet, Text, View, Button } from "react-native";

export default function DashboardScreen({ navigation }) {
    return (
        <View style={styles.container}>
            <Text style={styles.text}>DashboardScreen</Text>
            <Button
                title="Toggle drawer"
                onPress={() => navigation.toggleDrawer()}
            />
            <Button
                title="Settings"
                onPress={() => navigation.jumpTo("Settings")}
            />
        </View>
    );
}

const styles = StyleSheet.create({
    container: {
        flex: 1,
        backgroundColor: "#fff",
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

SettingScreen.js

```js
import { StyleSheet, Text, View } from "react-native";

export default function SettingScreen() {
    return (
        <View style={styles.container}>
            <Text style={styles.text}>SettingScreen</Text>
        </View>
    );
}

const styles = StyleSheet.create({
    container: {
        flex: 1,
        backgroundColor: "#fff",
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

Chú ý cái app.js DashboardScreen.js SettingScreen.js

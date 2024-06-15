# Navigation between Screens

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
            <Stack.Navigator initialRouteName="Home">
                <Stack.Screen name="Home" component={HomeScreen} />
                <Stack.Screen name="About" component={AboutScreen} />
            </Stack.Navigator>
        </NavigationContainer>
    );
}
```

Tạo Thư mục screens/HomeScreen.js

```js
import React from "react";
import { View, Text, Button, StyleSheet, Button } from "react-native";

export default function HomeScreen({ navigation }) {
    const navigation = useNavigation();
    return (
        <View style={styles.container}>
            <Text style={styles.text}>Home Screen</Text>
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

Khi nhấn vào button thì nó sẽ chuyển đến trang About, đồng nghĩa với việc trang about đi lên và chiếm vị trí đầu của trang Home

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

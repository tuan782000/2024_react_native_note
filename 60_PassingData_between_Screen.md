# Passing Data between Screens - Truyền dữ liệu giữa hai màn hình

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
// import { useNavigation } from "@react-navigation/native";

export default function HomeScreen({ navigation }) {
    // const navigation = useNavigation();
    return (
        <View style={styles.container}>
            <Text style={styles.text}>Home Screen</Text>
            <Text style={styles.text}>{route.params?.result}</Text>
            <Button
                title="Go to About"
                onPress={() =>
                    navigation.navigate("About", {
                        name: "Vishwas",
                    })
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

AboutScreen.js

```js
import React from "react";
import { View, Text, Button, StyleSheet } from "react-native";

export default function AboutScreen({ route }) {
    const { name } = route.params;
    return (
        <View style={styles.container}>
            <Text style={styles.text}>About Screen {name}</Text>
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

---

Phần 2:

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
                <Stack.Screen
                    name="About"
                    component={AboutScreen}
                    initialParams={{ name: "Guest" }}
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

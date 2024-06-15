# Stack Navigation Options

Theo dõi screenOptions và options

App.js

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

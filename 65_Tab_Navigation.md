# Tab Navigation

Tab Navigation offers a way to switch between different screens by tapping on a tab which is usually disabled at the bottom of the screen

Tab Navigation cung cấp một cách để chuyển đổi giữa các màn hình khác nhau bằng cách chạm vào một tab thường được đặt ở dưới cùng của màn hình.

It's common and intuitive navigation pattern found in many apps, providing a seamless, user-friendly experience

npm install @react-navigation/bottom-tabs

App.js

```js
import { NavigationContainer } from "@react-navigation/native";
import { createBottomTabNavigator } from "@react-navigation/bottom-tabs";
import CourseListScreen from "./screens/CourseListScreen";
import ProfileScreen from "./screens/ProfileScreen";
import SettingsScreen from "./screens/SettingsScreen";

const Tab = createBottomTabNavigator();

export default function App() {
    return (
        <NavigationContainer>
            <Tab.Navigator>
                <Tab.Screen name="Course List" component={CourseListScreen} />
                <Tab.Screen name="Profile" component={ProfileScreen} />
                <Tab.Screen name="Settings" component={SettingsScreen} />
            </Tab.Navigator>
        </NavigationContainer>
    );
}
```

ProfileScreen.js

```js
import { View, Text, StyleSheet } from "react-native";

const ProfileScreen = () => {
    return (
        <View style={styles.container}>
            <Text style={styles.text}>ProfileScreen</Text>
        </View>
    );
};

export default ProfileScreen;

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

CourseListScreen.js

```js
import { View, Text, StyleSheet } from "react-native";

const CourseListScreen = () => {
    return (
        <View style={styles.container}>
            <Text style={styles.text}>CourseListScreen</Text>
        </View>
    );
};

export default CourseListScreen;

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
})``;
```

SettingsScreen.js

```js
import { View, Text, StyleSheet } from "react-native";

const SettingsScreen = () => {
    return (
        <View style={styles.container}>
            <Text style={styles.text}>SettingsScreen</Text>
        </View>
    );
};

export default SettingsScreen;

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
})``;
```

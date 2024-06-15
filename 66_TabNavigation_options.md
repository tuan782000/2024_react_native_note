# Tab Navigation Options

quyết định xem icon nằm trên đầu. bên cạnh hay dưới chữ

tabBarLabelPosition: "beside-icon", // beside-icon nằm bên cạnh - tay trái của label

tabBarShowLabel: false, // quyết định show label hay không, false thì không show label, true thì show. Mặc định là true nên label show ra

tabBarActiveTintColor: "purple", // Quyết định màu sắc của icon và chữ sau khi được focus active

Các Items:

options= {
tabBarLabel: "My profile",
}

Quyết định tên cho label thay vì tự động lấy

tabBarIcon dùng để điều chỉnh icon bao gồm hình dạng kích thước và kích cở của cái icon

tabBarBadge con số biểu thị trên icon, giống tin nhắn của message thông báo bao nhiêu tin chưa đọc. Hoặc số đơn hàng đang có trong giỏ hàng

App.js

```js
import { NavigationContainer } from "@react-navigation/native";
import { createBottomTabNavigator } from "@react-navigation/bottom-tabs";
import CourseListScreen from "./screens/CourseListScreen";
import ProfileScreen from "./screens/ProfileScreen";
import SettingsScreen from "./screens/SettingsScreen";
import Ionicons from "@expo/vector-icons/Ionicons";

const Tab = createBottomTabNavigator();

export default function App() {
    return (
        <NavigationContainer>
            <Tab.Navigator
                screenOptions={{
                    tabBarLabelPosition: "beside-icon",
                    tabBarShowLabel: false,
                    tabBarActiveTintColor: "purple",
                }}
            >
                <Tab.Screen name="Course List" component={CourseListScreen} />
                <Tab.Screen
                    name="Profile"
                    component={ProfileScreen}
                    options={{
                        tabBarLabel: "My profile",
                        tabBarIcon: ({ color }) => (
                            <Ionicons name="person" size={20} color={color} />
                        ),
                        tabBarBadge: 3,
                    }}
                />
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

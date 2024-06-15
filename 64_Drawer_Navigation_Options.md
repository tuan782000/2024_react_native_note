# Drawer Navigation Options

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
                <Drawer.Screen
                    name="Dashboard"
                    component={DashboardScreen}
                    options={
                        title: "My dashboard", // tiêu đề cho trang
                        drawerLabel: "Dashboard label", // tên trong tab trượt ra
                        drawerActiveBackgroundColor: "lightBlue", // màu nền active
                        drawerContentStyle: {
                            backgroundColor: "#c6cbef", // màu nền của nguyên tab thò ra
                        }
                    }
                />
                <Drawer.Screen name="Settings" component={SettingScreen} />
            </Drawer.Navigator>
        </NavigationContainer>
    );
}
```

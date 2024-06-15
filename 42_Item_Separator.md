# ItemSeparatorComponent

```js
import {
    StyleSheet,
    View,
    Text,
    ScrollView,
    SafeAreaView,
    StatusBar,
    FlatList,
} from "react-native";
import pokemonList from "./data.json";

export default function App() {
    return (
        <SafeAreaView style={styles.container}>
            <View style={styles.scrollView}>
                <FlatList
                    data={pokemonList}
                    renderItem={({ item }) => {
                        console.log(item.id); // nó sẽ load đâu đó khoảng 64 items mà không load hết tất cả items
                        return (
                            <View style={styles.card} key={item.id}>
                                <Text style={styles.cardText}>{item.type}</Text>
                                <Text style={styles.cardText}>{item.name}</Text>
                            </View>
                        );
                    }}
                    KeyExtractor={(item) => item.id.toString()}
                    <ItemSeparatorComponent={<View style={{ height: 16 }}/>}
                />
            </View>
        </SafeAreaView>
    );
}

const styles = StyleSheet.create({
    container: {
        flex: 1,
        backgroundColor: "#f5f5f5",
        paddingTop: StatusBar.currentHeight,
    },
    scrollView: {
        paddingHorizontal: 16,
    },
    card: {
        backgroundColor: "White",
        padding: 16,
        borderRadius: 8,
        borderWidth: 1,
    },
    cardText: {
        fontSize: 30,
    },
});
```

ItemSeparatorComponent giúp ta cách nhau giữa các item 1 đoạn mà ta quy định mà không cần marginBottom: 16, giữa các item

Như đã tìm hiểu bài trước ta có tìm hiểu về List, sau đó dùng map lặp qua để tạo ra danh sách

Cách này chỉ nên áp dụng với các danh sách nhỏ.

Nó sẽ bất lợi khi gặp 1 danh sách lớn

Chính vì vậy react native cho ra đời FlatList

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
        marginBottom: 16,
    },
    cardText: {
        fontSize: 30,
    },
});
```

Bài tập chuyển danh sách này thành cuộn ngang

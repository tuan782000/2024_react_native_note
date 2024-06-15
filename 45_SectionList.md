# SectionList

A performant component designed for rendering sectioned lists

grouped-data.json

```js
[
    {
        type: "Grass",
        data: ["Bulbasaur", "Ivysaur", "Venusaur"],
    },
    {
        type: "Fire",
        data: ["Charmander", "Charmeleon", "Charizard"],
    },
    {
        type: "Water",
        data: ["Squirtle", "Wartortle", "Blastoise"],
    },
    { type: "Electric", data: ["Pikachu", "Raichu"] },
];
```

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
import groupedPokemonList from "./grouped-data.json";

export default function App() {
    return (
        <SafeAreaView style={styles.container}>
            <View style={styles.scrollView}>
                <SectionList
                    sections={groupedPokemonList}
                    renderItem={({ item }) => {
                        return (
                            <View style={styles.card}>
                                <Text style={styles.cardText}>{item}</Text>
                            </View>
                        );
                    }}
                    renderSectionHeader={({ section }) => {
                        <Text style={styles.sectionHeaderText}>
                            {section.type}
                        </Text>;
                    }}
                    ItemSeparatorComponent={() => (
                        <View style={{ height: 16 }} />
                    )}
                    SectionSeparatorComponent={() => (
                        <View style={{ height: 16 }} />
                    )}
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
    headerText: {
        fontSize: 24,
        textAlign: "center",
        marginBottom: 12,
    },
    footerText: {
        fontSize: 24,
        textAlign: "center",
        marginBottom: 12,
    },
    sectionHeaderText: {
        backgroundColor: "white",
        fontSize: 24,
        fontWeight: "bold",
    },
});
```

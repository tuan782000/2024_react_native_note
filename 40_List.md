Lists

Rendering lists is an essential aspect of mobile application development.

Whether it's a list of contacts, products, or any other collection of items, lists are a fundamental UI component

Duyệt danh sách là một khía cạnh quan trọng của việc phát triển ứng dụng di động.

Cho dù đó là một danh sách các liên hệ, sản phẩm hoặc bất kỳ bộ sưu tập mục nào khác, danh sách đều là một thành phần giao diện người dùng cơ bản.

data.json

```js
[
    { id: "1", type: "Grass", name: "Bulbasaur" },
    { id: "2", type: "Grass", name: "Ivysaur" },
    { id: "3", type: "Grass", name: "Venusaur" },
    { id: "4", type: "Fire", name: "Charmander" },
    { id: "5", type: "Fire", name: "Charmeleon" },
    { id: "6", type: "Fire", name: "Charizard" },
    { id: "7", type: "Water", name: "Squirtle" },
    { id: "8", type: "Water", name: "Wartortle" },
    { id: "9", type: "Water", name: "Blastoise" },
    { id: "10", type: "Bug", name: "Caterpie" },
    { id: "11", type: "Bug", name: "Metapod" },
    { id: "12", type: "Bug", name: "Butterfree" },
    { id: "13", type: "Normal", name: "Pidgey" },
    { id: "14", type: "Normal", name: "Pidgeotto" },
    { id: "15", type: "Normal", name: "Pidgeot" },
    { id: "16", type: "Electric", name: "Pikachu" },
    { id: "17", type: "Electric", name: "Raichu" },
    { id: "18", type: "Ground", name: "Sandshrew" },
    { id: "19", type: "Ground", name: "Sandslash" },
    { id: "20", type: "Poison", name: "Nidoran" },
    { id: "21", type: "Poison", name: "Nidorina" },
    { id: "22", type: "Poison", name: "Nidoqueen" },
    { id: "23", type: "Poison", name: "Nidorino" },
    { id: "24", type: "Poison", name: "Nidoking" },
    { id: "25", type: "Electric", name: "Voltorb" },
    { id: "26", type: "Electric", name: "Electrode" },
    { id: "27", type: "Ground", name: "Diglett" },
    { id: "28", type: "Ground", name: "Dugtrio" },
    { id: "29", type: "Psychic", name: "Abra" },
    { id: "30", type: "Psychic", name: "Kadabra" },
    { id: "31", type: "Psychic", name: "Alakazam" },
    { id: "32", type: "Fighting", name: "Machop" },
    { id: "33", type: "Fighting", name: "Machoke" },
    { id: "34", type: "Fighting", name: "Machamp" },
    { id: "35", type: "Ice", name: "Jynx" },
    { id: "36", type: "Ice", name: "Lapras" },
    { id: "37", type: "Ghost", name: "Gastly" },
    { id: "38", type: "Ghost", name: "Haunter" },
    { id: "39", type: "Ghost", name: "Gengar" },
    { id: "40", type: "Rock", name: "Geodude" },
    { id: "41", type: "Rock", name: "Graveler" },
    { id: "42", type: "Rock", name: "Golem" },
    { id: "43", type: "Water", name: "Horsea" },
    { id: "44", type: "Water", name: "Seadra" },
    { id: "45", type: "Grass", name: "Oddish" },
    { id: "46", type: "Grass", name: "Gloom" },
    { id: "47", type: "Grass", name: "Vileplume" },
    { id: "48", type: "Normal", name: "Meowth" },
    { id: "49", type: "Normal", name: "Persian" },
    { id: "50", type: "Fire", name: "Growlithe" },
    { id: "51", type: "Fire", name: "Arcanine" },
    { id: "52", type: "Water", name: "Poliwag" },
    { id: "53", type: "Water", name: "Poliwhirl" },
    { id: "54", type: "Water", name: "Poliwrath" },
    { id: "55", type: "Psychic", name: "Kadabra" },
    { id: "56", type: "Psychic", name: "Alakazam" },
    { id: "57", type: "Fighting", name: "Machop" },
    { id: "58", type: "Fighting", name: "Machoke" },
    { id: "59", type: "Fighting", name: "Machamp" },
    { id: "60", type: "Ice", name: "Jynx" },
    { id: "61", type: "Ice", name: "Lapras" },
    { id: "62", type: "Ghost", name: "Gastly" },
    { id: "63", type: "Ghost", name: "Haunter" },
    { id: "64", type: "Ghost", name: "Gengar" },
    { id: "65", type: "Rock", name: "Onix" },
    { id: "66", type: "Bug", name: "Krabby" },
    { id: "67", type: "Bug", name: "Kingler" },
    { id: "68", type: "Normal", name: "Rattata" },
    { id: "69", type: "Normal", name: "Raticate" },
    { id: "70", type: "Flying", name: "Spearow" },
    { id: "71", type: "Flying", name: "Fearow" },
    { id: "72", type: "Electric", name: "Magnemite" },
    { id: "73", type: "Electric", name: "Magneton" },
    { id: "74", type: "Ground", name: "Cubone" },
    { id: "75", type: "Ground", name: "Marowak" },
    { id: "76", type: "Poison", name: "Zubat" },
    { id: "77", type: "Poison", name: "Golbat" },
    { id: "78", type: "Fire", name: "Vulpix" },
    { id: "79", type: "Fire", name: "Ninetales" },
    { id: "80", type: "Water", name: "Jigglypuff" },
    { id: "81", type: "Water", name: "Wigglytuff" },
    { id: "82", type: "Grass", name: "Zubat" },
    { id: "83", type: "Grass", name: "Golbat" },
    { id: "84", type: "Normal", name: "Ekans" },
    { id: "85", type: "Normal", name: "Arbok" },
    { id: "86", type: "Fire", name: "Pikachu" },
    { id: "87", type: "Fire", name: "Raichu" },
    { id: "88", type: "Water", name: "Dratini" },
    { id: "89", type: "Water", name: "Dragonair" },
    { id: "90", type: "Dragon", name: "Dragonite" },
    { id: "91", type: "Fairy", name: "Clefairy" },
    { id: "92", type: "Fairy", name: "Clefable" },
    { id: "93", type: "Ice", name: "Seel" },
    { id: "94", type: "Ice", name: "Dewgong" },
    { id: "95", type: "Psychic", name: "Grimer" },
    { id: "96", type: "Psychic", name: "Muk" },
    { id: "97", type: "Fighting", name: "Shellder" },
    { id: "98", type: "Fighting", name: "Cloyster" },
    { id: "99", type: "Flying", name: "Gastly" },
    { id: "100", type: "Flying", name: "Haunter" },
];
```

App.js

```js
import {
    StyleSheet,
    View,
    Text,
    ScrollView,
    SafeAreaView,
    StatusBar,
} from "react-native";
import pokemonList from "./data.json";

export default function App() {
    return (
        <SafeAreaView style={styles.container}>
            <ScrollView style={styles.paddingHorizontal}>
                {pokemonList.map((pokemon) => {
                    return (
                        <View style={styles.card} key={pokemon.id}>
                            <Text style={styles.cardText}>{pokemon.type}</Text>
                            <Text style={styles.cardText}>{pokemon.name}</Text>
                        </View>
                    );
                })}
            </ScrollView>
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

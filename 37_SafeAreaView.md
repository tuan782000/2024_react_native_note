SafeAreaView

Như lúc trước chưa dùng SafeAreaView, View flex 1 thì nó sẽ lấy full màn hình, động chạm IOS dynamic island.

Khi dùng SafeAreaView thì nó sẽ chừa các phần đó ra, việc của ta cho vùng SafeAreaView nó flex: 1 chiếm hết những phần của nó được chiếm sau đó đổi màu sao cho trùng với background

```js
import { StyleSheet, View, Text, SafeAreaView } from "react-native";

export default function App() {
    return (
        <SafeAreaView style={styles.safeContainer}>
            <View style={styles.container}>
                <View style={styles.box}>
                    <Text style={styles.text}>Welcome!</Text>
                </View>
            </View>
        </SafeAreaView>
    );
}

const styles = StyleSheet.create({
    safeContainer: {
        flex: 1,
        backgroundColor: "plum",
    },
    container: {
        flex: 1,
        backgroundColor: "plum",
        alignItems: "center",
        justifyContent: "center",
    },
    box: {
        width: windowWidth > 500 ? "70%" : "90%",
        height: windowHeight > 600 ? "60%" : "90%",
        backgroundColor: "lightblue",
        alignItems: "center",
        justifyContent: "center",
    },
    text: {
        fontSize: windowWidth > 500 ? 50 : 24,
    },
});
```





```js
import React from 'react';
import {
  View,
  KeyboardAvoidingView,
  TextInput,
  StyleSheet,
  Text,
  Platform,
  TouchableWithoutFeedback,
  Button,
  Keyboard,
  ScrollView,
  SafeAreaView
} from 'react-native';

const KeyboardAvoidingComponent = () => {
  return (
  <SafeAreaView style={{flex: 1}}>
    <KeyboardAvoidingView
      behavior={Platform.OS === 'ios' ? 'padding' : 'height'}
      style={styles.container}
      keyboardVerticalOffset={20}
      >
      <TouchableWithoutFeedback onPress={Keyboard.dismiss}>
        <ScrollView style={styles.inner}>
          <Text style={styles.header}>Header</Text>
          <TextInput placeholder="Username" style={styles.textInput} />
          <TextInput placeholder="Username" style={styles.textInput} />
          <TextInput placeholder="Username" style={styles.textInput} />
          <TextInput placeholder="Username" style={styles.textInput} />
          <TextInput placeholder="Username" style={styles.textInput} />
          <TextInput placeholder="Username" style={styles.textInput} />
          <TextInput placeholder="Username" style={styles.textInput} />
          <TextInput placeholder="Username" style={styles.textInput} />
          <TextInput placeholder="Username" style={styles.textInput} />
          <TextInput placeholder="Username" style={styles.textInput} />
          <TextInput placeholder="Username" style={styles.textInput} />
          <TextInput placeholder="Username" style={styles.textInput} />
          
          <View style={styles.btnContainer}>
            <Button title="Submit" onPress={() => null} />
          </View>
        </ScrollView>
      </TouchableWithoutFeedback>
    </KeyboardAvoidingView>
    </SafeAreaView>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
  },
  inner: {
    padding: 24,
    flex: 1,
    justifyContent: 'flex-start',
  },
  header: {
    fontSize: 36,
    marginBottom: 48,
  },
  textInput: {
    height: 40,
    borderColor: '#000000',
    borderBottomWidth: 1,
    marginBottom: 36,
  },
  btnContainer: {
    backgroundColor: 'white',
    marginTop: 12,
  },
});

export default KeyboardAvoidingComponent;
```

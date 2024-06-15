# Networking - Get - Loading - Pull to Refresh kéo để reload - Post request

Fetching and Submitting data to an API

Loading states

Error handling

FlatList component to dissplay our data

https://jsonplaceholder.typicode.com/

https://jsonplaceholder.typicode.com/posts

Giới hạn 10 item

https://jsonplaceholder.typicode.com/posts?_limit=10

```js
import {
    SafeAreaView,
    StyleSheet,
    Text,
    View,
    FlatList,
    ActivityIndicator,
    TextInput,
    Button,
} from "react-native";
import { useState, useEffect } from "react";

export default function App() {
    const [postList, setPostList] = useState([]);
    const [isLoading, setIsLoading] = useState(true);
    const [refreshing, setRefreshing] = useState(false);

    const [postTitle, setPostTitle] = useState("");
    const [postBody, setPostBody] = useState("");
    const [isPosting, setIsPosting] = useState(false); // theo dõi quá trình gửi dữ liệu

    const [error, setError] = useState("");

    const fetchData = async (limit = 10) => {
        try {
            const response = await fetch(
                `https://jsonplaceholder.typicode.com/posts?_limit=${limit}`
            );

            const data = await response.json();
            setPostList(data);
            setIsLoading(false);
            setError("");
        } catch (error) {
            console.error("Error fetching data:" + error);
            setIsLoading(false);
            setError("Failed to fetch post list");
        }
    };

    const handleRefresh = () => {
        setRefreshing(true);
        fetchData(20);
        setRefreshing(false);
    };

    const addPost = async () => {
        setIsPosting(true);
        try {
            // ngoài fetch sử dụng axios hoặc tan stack query
            const response = await fetch(
                "https://jsonplaceholder.typicode.com/posts",
                {
                    method: "POST",
                    headers: {
                        "Content-type": "application/json",
                    },
                    body: JSON.stringify({
                        title: postTitle,
                        body: postBody,
                    }),
                }
            );

            const newPost = await response.json();
            setPostList([newPost, ...postList]); // thực hiện thêm newPost vào danh sách postList bằng cách sử dụng setPostList
            // ... trải mảng postList ra để thêm newPost vào
            setPostTitle("");
            setPostBody("");
            setIsPosting(false);
            setError("");
        } catch (error) {
            console.error("Error adding new post: ", error);
            setError("Failed to add new post");
        }
    };

    useEffect(() => {
        fetchData();
    }, []);

    if (isLoading) {
        return (
            <SafeAreaView styles={styles.loadingContainer}>
                <ActivityIndicator size="large" color="0000ff" />
                <Text>Loading...</Text>
            </SafeAreaView>
        );
    }

    return (
        <SafeAreaView style={styles.container}>
            {error ? (
            <View style={styles.errorContainer}>
                <Text style={styles.errorText}>{error}</Text>
            </View>
            ) : (<>
                <View style={styles.inputContainer}>
                    <TextInput
                        style={styles.input}
                        placeholder="Post title"
                        value={postTitle}
                        onChangeText={setPostTitle}
                    />
                    <TextInput
                        style={styles.input}
                        placeholder="Post body"
                        value={postBody}
                        onChangeText={setPostBody}
                    />
                    <Button
                        title={isPosting ? "Adding..." : "Add Post"}
                        onPress={addPost}
                        disabled={isPosting}
                    />
                </View>
                <View style={styles.listContainer}>
                    <FlatList
                        data={postList}
                        renderItem={({ item }) => {
                            return (
                                <View style={styles.card}>
                                    <Text style={styles.titleText}>
                                        {item.title}
                                    </Text>
                                    <Text style={styles.bodyText}>
                                        {item.body}
                                    </Text>
                                </View>
                            );
                        }}
                        ItemSeparatorComponent={() => {
                            <View
                                style={{
                                    height: 16,
                                }}
                            />;
                        }}
                        ListEmptyComponent={<Text>No Posts Not Found</Text>}
                        ListHeaderComponent={
                            <Text style={styles.headerText}>Post List</Text>
                        }
                        ListFooterComponent={
                            <Text style={styles.footerText}>End of list</Text>
                        }
                        refreshing={refreshing}
                        onRefresh={handleRefresh}
                    />
                </View>
            </>)}
        </SafeAreaView>
    );
}

const styles = StyleSheet.create({
    container: {
        flex: 1,
        backgroundColor: "#f5f5f5",
        paddingTop: StatusBar.currentHeight,
    },
    listContainer: {
        flex: 1,
        paddingHorizontal: 16,
    },
    card: {
        backgroundColor: "white",
        padding: 16,
        borderRadius: 8,
        borderWidth: 1,
    },
    titleText: {
        fontSize: 30,
    },
    bodyText: {
        fontSize: 24,
        color: "#666666",
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
    loadingContainer: {
        flex: 1,
        backgroundColor: "#f5f5f5",
        paddingTop: StatusBar.currentHeight,
        justifyContent: "center",
        alignItems: "center",
    },
    inputContainer: {
        backgroundColor: "white",
        padding: 16,
        borderRadius: 8,
        borderWidth: 1,
        margin: 16,
    },
    input: {
        height: 40,
        borderColor: "gray",
        borderWidth: 1,
        marginBottom: 8,
        padding: 8,
        borderRadius: 8,
    },
    errorContainer: {
        backgroundColor: '#FFC0CB',
        padding: 16,
        borderRadius: 8,
        borderWidth: 1
        margin: 16
        alignItems: 'center'
    },
    errorText: {
        color: '#D8000C',
        fontSize: 16,
        textAlign: 'center'
    }
});
```

Chú ý android localhost không hoạt động trên máy giả lập nhưng ios thì có thể, thay vào đó hãy dụng IP address

đoạn cuối có hướng dẫn mở debugger trên Iphone

https://www.youtube.com/watch?v=ZvobN5Hn_4s&list=PLC3y8-rFHvwhiQJD1di4eRVN30WWCXkg1&index=71

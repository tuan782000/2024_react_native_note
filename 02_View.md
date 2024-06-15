# View trong react-native

The view component is a fundamental core component in React Native that serves as building block for creating user interface

It function as a container that supports layout using flexbox, styling, touch, handling and accessibility controls

In web development terms, the view component can be compared to the 'div' tag

The View component is typically nested inside other views and have zero or more children of any type

"Thành phần View có thể được lồng bên trong các Views khác và có không hoặc các con của bất kỳ loại nào"

Muốn sử dụng được view bên trong thu viện react native

```js
// App.js
import { View } from "react-native";

export default function App() {
    return <View style={{ backgroundColor: "plum" }}></View>;
}
```

Nên nhớ

View component only takes up the space occupied by its children and currently we haven't added any children to the View

Thành phần view chỉ chiếm không gian bị con của nó chiếm giữ và hiện tại chúng ta chưa có thêm bất kỳ children cho View

Ví dụ trên: backgroundColor sẽ không hoạt động, vì View không có thằng con nào cả

to make the view occupy the entire available space we need to specify another style property

Để cho khung hình view chiếm toàn bộ không gian có sẵn chúng ta cần chỉ định thuộc tính style khác

Bổ sung thuộc tính flex: 1

```js
// App.js
import { View } from "react-native";

export default function App() {
    return <View style={{ flex: 1, backgroundColor: "plum" }}></View>;
}
```

View will flexibly expand and take up all available space on screen

view sẽ linh hoạt mở rộng và chiếm dụng tất cả khoảng trống có sẵn trong màn hình

The main takeaway here is to remember to import the view component before using it and understand that it serves as a container for other components

Điều chính rút ra ở đây là hãy nhớ rằng import thằng view component trước khi sử dụng nó và hiểu được nó phục vụ như là thùng chứa cho 1 component khác

Giờ ta sẽ thử nest(lồng 2 view)

```js
// App.js
import { View } from "react-native";

export default function App() {
    return (
        <View style={{ flex: 1, backgroundColor: "plum" }}>
            <View
                style={{
                    width: 200,
                    height: 200,
                    backgroundColor: "lightblue",
                }}
            ></View>
            <View
                style={{
                    width: 200,
                    height: 200,
                    backgroundColor: "lightgreen",
                }}
            ></View>
        </View>
    );
}
```

flex: 1 cho một thành phần View, nó sẽ mở rộng để chiếm tối đa không gian có sẵn. width và height 100%

Bây giờ bên trong View có 2 view con và mỗi thằng có chiều rộng và cao riêng có màu sắc riêng, thằng trên sẽ nằm trên thằng dưới sẽ bị đẩy xuống



```js
import React from 'react';
import {View, Text} from 'react-native';

const ViewBoxesWithColorAndText = () => {
  return (
    <View
      style={{
        flexDirection: 'row',
        height: 100,
        padding: 20,
      }}>
      <View style={{backgroundColor: 'blue', flex: 1}} />
      <View style={{backgroundColor: 'red', flex: 1}} />
      <Text>Hello World!</Text>
    </View>
  );
};

export default ViewBoxesWithColorAndText;
```

View chiếm hết chiều ngang, nếu set chiều cao cho nó thì nó chiếm chiều cao đó trở thành HCN

Nếu ta muốn các View nằm trên cùng 1 hàng Flex direction row để lên 1 hàng.

Độ rộng của View sẽ không còn chiếm hết 1 hàng nếu đã nằm trên cùng 1 hàng. Lúc này ta có thể dùng flex để set hoặc đặt width cứng

Để co giản linh động cứ set flex 1 cho View đó


Nếu bạn set width thì dùng flexWrap: 'wrap'  được, còn dùng flex thì sẽ không hoạt động với flexWrap: 'wrap'

Ví dụ

```js
import React from 'react';
import {View, Text} from 'react-native';

const ViewBoxesWithColorAndText = () => {
  return (
    <View
      style={{
        flexDirection: 'row',
        flexWrap: 'wrap',
        height: 100,
        padding: 20,
      }}>
      <View style={{backgroundColor: 'blue', flex: 1 }} /> {/*Chỗ này phải đặt width cụ thể nó mới xuống hàng được*/}
      <View style={{backgroundColor: 'red' , flex: 1}} /> {/*View flex sẽ co giản và chiếm hết phần còn lại*/}
      <Text>Hello World!</Text>
    </View>
  );
};

export default ViewBoxesWithColorAndText;
```

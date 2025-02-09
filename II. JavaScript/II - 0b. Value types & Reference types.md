## Value types (tham trị)
- Khai báo và sử dụng 1 lần duy nhất tại 1 thời điểm.
- Là các kiểu **primitive types** như: number, string, boolean, symbol, undefined, null.
```
let x = 10;
let y = x;
x = 12;
console.log(x) // 12
console.log(y) // 10
```
- Khi gán một biến y bằng giá trị biến hiện tại x, thì **bản sao (x coppy)** của biến hiện tại x sẽ gán cho biến mới y.
- Hai biến đều độc lập với nhau nên khi thay đổi giá trị của biến (x) sẽ không ảnh hưởng đến biến (y).
## Reference types (tham chiếu)
- Tham chiếu đến địa chỉ của giá trị.
- Gồm có non-primitive type: object, array; function.
```
let x = {value: 10};
let y = x;
x.value = 15;
console.log(x) // {value: 15}
console.log(y) // {value: 15}
```
![[valuetype-and-referencetype.png]]
- Khác với value types, reference type là kiểu tham chiếu, nó lưu địa chỉ giá trị mà nó đang chứa, chứ không phải giá trị đó.
- Nên khi gán obj y = obj x, tức là đang coppy địa chỉ x đang chứa qua cho y. Nói cách khác thì x & y đang cùng chỉ đến một obj trong bộ nhớ khi coppy.
## Summary
- Primitives are copied by their value.
- Objects are copied by their reference.

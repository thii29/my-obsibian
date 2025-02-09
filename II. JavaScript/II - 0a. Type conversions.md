#### String conversion
```
let value = 29;
value = String(value);
console.log(typeof value); //value lúc này đã được convert thành string
```
#### Numeric  conversion
```
let data = "6"/"3";
console.log(data); //lúc này data là number vì chuỗi ko thể thực hiện toán tử
//js ép kiểu thành numeric để thực hiện phép tính

let value = "21";
value = Number(value);
console.log(data); // value lúc này là number

//nếu chuỗi không phải là số hợp lệ thì khi ép kiểu number nó sẽ trả về NaN
let age = Number("an arbitrary string instead of a number");
alert(age); // NaN, conversion failed
```
*Numeric converion rules:*
- undefined → NaN
- null → 0
- true and false → 1 and 0
- string (empty) → 0, but Number(298thi) → NaN
#### Boolean conversion
```
Boolean(1); // true
Boolean(0); // false
Boolean("meowmeow"); // true
Boolean(""); // false
```

- `0`, `null`, `undefined`, `NaN`, `""`(chuỗi rỗng) → `false` (*Falsy value*)
- any other value → `true`
- `"0"` and space-only strings like `" "` are `true` as a boolean.
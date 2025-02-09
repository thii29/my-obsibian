### Thêm/ xoá phần tử trong mảng (Add/ remove elements)
- **push(item):** thêm item vào cuối mảng (add items to the end).
- **pop():** lấy item từ cuối mảng (extracts an item from the end).
- **shift():** lấy item ở đầu mảng (extracts an item from the beginning).
- **unshift(...items):** thêm item vào đầu mảng (adds items to the beginning).
	        ![[shift:push.png]]                            ![[push:pop.png]]
```
//shift & push
let arr = ['orange', 'banana', 'kiwi']
arr.push('lemon')
console.log(arr) //['orange', 'banana', 'kiwi', 'lemon']

arr.shift()
console.log(arr) //['banana', 'kiwi', 'lemon']

//push, pop & unshift
let array = ["1a", "2e", "3f", "4s","5z"]
array.unshift("0d")
console.log(array) // ['0d', '1a', '2e', '3f', '4s', '5z']

array.pop()
console.log(array) // ['0d', '1a', '2e', '3f', '4s']

array.push("5g")
console.log(array) // ['0d', '1a', '2e', '3f', '4s', '5g']
```
- **concat():** gộp 2 hoặc nhiều array/ string thành 1 array/ string mới (combines 2 arrays/ strings into the new one)
**Syntax: array.concat(arr1, arr2,...)**
```
let arrCombine = arr.concat(array)
console.log(arrCombine)
=> ['banana', 'kiwi', 'lemon', '0d', '1a', '2e', '3f', '4s', '5g']
```
- **slice(start, end):** trả về một mảng mới coppy từ mảng cũ bắt đầu từ vị trí start đến vị trí end -1 (It returns a new array copying to it all items from index start to before end (not including end) ). Lưu ý: nếu không thêm tham số thì slice sẽ clone mảng ban đầu ra
**Syntax: arr.slice([start], [end])**
``` 
let subArr = arrCombine.slice(2, 8)
console.log(subArr)
=> ['lemon', '0d', '1a', '2e', '3f', '4s']
```
- **splice():** thêm, xoá hoặc thay thế phần tử trong mảng ban đầu (insert, remove and replace elements in original array). 
**Syntax: arr. splice(start, deleteCount, item1, item2,...itemN)***
```
//Insert element(s)
let array = ["January", "February", "April", "June"]
array.splice(2,0,"March")
console.log(array) // ['January', 'February', 'March', 'April', 'June']

//Replace elemnt(s)
array.splice(4, 1, "May")
console.log(array) //['January', 'February', 'March', 'April', 'May']

//Remove element(s)
array.splice(4, 1)
console.log(array) //['January', 'February', 'March', 'April']
```
### Tìm phần tử (Searching among elements)
- **filter((item, index, array) => { })**: trả về mãn chứa phần tử thoả điều kiện (return a new array rely on condition)
```
Write a function `filterRange(arr, a, b)` that gets an array `arr`, looks for elements with values higher or equal to `a` and lower or equal to `b` and return a result as an array.

let arr = [5, 3, 8, 1, 2];
function filterRange (arr, a, b){
	return arr.filter(item => {return (a <= item && item <= b)})
}

let filtered = filterRange(arr, 1, 4);
console.log(filtered) // [3, 1, 2]
```
- **find((item, index, array) => { })**: trả về *item đầu tiên đúng điều kiện*, undefined nếu không thấy (If it returns true, the search is stopped, the item is returned. If nothing found, undefined is returned).
```
// Array string
const words = ["apple", "banana", "cherry", "date", "elderberry"];
const longWord = words.find(word => word.length > 5);
console.log(longWord); // Output: "banana"

//Array number
const numbers = [3, 7, 10, 15, 20];
const numberAboveTen = numbers.find(number => number > 10);
console.log(numberAboveTen); // Output: 15

//Array object
const people = [
  { name: "Alice", age: 22 },
  { name: "Bob", age: 28 },
  { name: "Charlie", age: 24 },
  { name: "David", age: 30 }
];
const personAbove25 = people.find(person => person.age > 25);
console.log(personAbove25); // Output: { name: "Bob", age: 28 }

```
- **includes()**: nếu mảng có phần tử thoả điều kiện thì trả về true, ngược lại false. Tóm lại là kiểm tra tồn tại.(returns true if the array has value, otherwise false)
```
//Array string
const fruits = ["apple", "banana", "cherry", "date", "elderberry"];
const hasBanana = fruits.includes("banana");
console.log(hasBanana); // Output: true

//Array number
const numbers = [3, 7, 10, 15, 20];
const containsFifteen = numbers.includes(15);
console.log(containsFifteen); // Output: true
```
Includes không thể kiểm tra trực tiếp thuộc tính của object vì vậy sẽ xài **some()** thay thế.
```
const people = [
  { name: "Alice", age: 22 },
  { name: "Bob", age: 28 },
  { name: "Charlie", age: 24 },
  { name: "David", age: 30 }
];

const containsBob = people.some(person => person.name === "Bob");
console.log(containsBob); // Output: true

```
- **indexOf()/ lastIndexOf(item, pos)**: look for item starting from position pos, return the index or 1 if not found.
- **findIndex()**: is like find, but returns the index instead of a value.
### Chuyển đổi mảng (Transform the array)
- **map(callbackFn)**:  cung cấp callback func tạo ra một mảng mới thoả mãn điều kiện (creates a new array from results of calling func for every element).
```
const numbers = [1, 2, 3, 4, 5];
const doubledNumbers = numbers.map(number => number * 2);
console.log(doubledNumbers); // Output: [2, 4, 6, 8, 10]

//Array Object
const people = [
  { name: "Alice", age: 22 },
  { name: "Bob", age: 28 },
  { name: "Charlie", age: 24 },
  { name: "David", age: 30 }
];

const peopleNextYear = people.map(person => ({
  name: person.name,
  nextYearAge: person.age + 1
}));

console.log(peopleNextYear);
// Output: [
//   { name: "Alice", nextYearAge: 23 },
//   { name: "Bob", nextYearAge: 29 },
//   { name: "Charlie", nextYearAge: 25 },
//   { name: "David", nextYearAge: 31 }
// ]
```
- **reduce(callbackFn, initialValue)**:  tương tự như 1 vòng lặp for, reduce duyệt qua tất cả phần tử trong mảng để tính toán và trả về một kết quả duy nhất.
**Syntax:** 
``` 
let value = arr.reduce(function(accumulator, item, index, array){
	// ...
},[initial]);
```

```
//Initial value
let numbers = [1,2,3,4]
let result = numbers.rerduce((accumulator, currentNum)=>{
	accumulator + currentNum
}, 1)
console.log(rersult) //11

//Without initial value
let numbers = [1,2,3,4]
let result = numbers.rerduce((accumulator, currentNum)=>{
	accumulator + currentNum
})
console.log(rersult) //10
```
- **sort()**: sắp xếp lại thứ tự các phần tử trong mảng (sorts the array in-place, then returns it).
- **reverse()**: đảo ngược thứ tự các phần tử trong mảng (reverses the array in-place, then returns it).
- **split()**: tách chuỗi ra thành mảng (divided string become array)
- **join()**: gộp phần tử trong mảng thành 1 chuỗi (combine)
## For
```
for(let i = 0, i < 5, i++){ 
	//điểm khởi tạo bước nhảy, đièu kiện, bước nhảy
	console.log("i-", i)
}
```
## For...in
Duyệt qua tất cả key trong object (Iterating over all the keys of an object).
```
for(key in object){
	statement
}
```
## For...of
Hoạt động trên các dãy giá trị lặp đi lặp lại được sắp xếp theo thứ tự, như array, string (Operating on a range of values sourced from an iterable, one by one in sequential order).
```
for(variable of array){
	statement
}
```
|              |  Object  |  Array/ String  | 
|--------|---------|---------------|
| for        |       x       |            o           |
| for ...in |       o       |            o (*xài được nhưng chỉ duyệt key (tức index) không duyệt value*)   |
| for ...of |       x       |            o           |



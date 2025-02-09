## Hoisting
Là hành động mặc định của Javascript, nó sẽ di chuyển các khai báo (như khai báo biến, khai báo hàm) lên đầu trước khi các câu lệnh được thực thi.
## Var, Let & Const
### Var
- Là từ khoá được sử dụng để khai báo biến.
- **Không có block scope.**
- Các giá trị được gán cho biến khai báo bởi var có thể thay đổi hoặc gán giá trị mới.
```
var a = 2;
a++
console.log(a) // a = 3;
```
- **var có cơ chế hoisting, được hoist lên đầu và khởi tạo giá trị là undefined**. Các biến khai báo bởi var có thể được gọi trước khi được định nghĩa vì theo cơ chế hoisting thì các khai báo var sẽ được di chuyển lên đầu đoạn script.
```
{
    var a = 2;
    {
        var a = 3;
        console.log("inside",a) // a = 3
    }
    console.log("outside",a) // a = 3
}
```
### Let
- Tương tự như var, là từ khoá sử dụng để khai báo biến. Các biến khai báo bởi let có thể thay đổi giá trị mới, hoặc gán giá trị mới.
- **Có block scope.**
- Có cơ chế hoisting nhưng phạm vi chỉ nằm trong block scope nhất định.
- Tạo ra 1 vùng temperal dead zone cho tới khi nó được khai báo. (Không tạo ra giá trị nào nếu cố gắng truy cập đến nó  trước khi được khai báo).
```
{
	let a = 2;
	{
		let a = 3;
		console.log("inside", a); // 3
	}
	console.log("outside", a); // 2
}
```
### Const
- Là từ khoá khai báo hằng.
- **Có block scope.**
- Các biến được khai báo bởi const sẽ không thể thay đổi giá trị
-  Có cơ chế hoisting và phạm vi hoisting cũng nằm trong block scope nhất định như let. 
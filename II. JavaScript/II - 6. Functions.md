## Declaration function
Còn gọi Global function vì nó tồn tại suốt đoạn script ⇠ do thuật toán nội bộ của JS sau khi chạy script sẽ tìm declaration function trước (cho nên declaration dunction có thể được gọi trước khi được khởi tạo, tương tự **hoisting** - [[II - 7. var, let, const & hoisting]]).
#### Syntax
```
function nameOfFunction(parameter, text = "default values"){
	/* code chức năng */
}
```
### Explain
- Paramater là tham số khi khai báo hàm, còn khi gọi hàm thì parameter chính là argument (đối số).
- Text sẽ có giá trị default là "default values" khi nó không được gán giá trị mới.
- Đoạn code được bao bởi dấu " {} " được gọi là building block.
- Khi hàm không định nghĩa thì sẽ trả về undefined.
- Không được thêm dòng cách giữa return và value
```
return 
(some + long + expression + or + whatever * f(a) + f(b))
// khi viết như trên, code sẽ hoạt động theo như dưới đây:
return; // thấy dấu chấm phẩy ko? 
(some + long + expression + or + whatever * f(a) + f(b))
// tức là nó sẽ không trả về đoạn giá trị trong ngoặc kia, do khi xuống dòng thì nó sẽ auto hiểu là return; ...

// thay vì viết như line 1 + 2, thì viết như sau:
return ( 
some + long + expression + 
or + whatever * f(a) + f(b) )
```
## Expression Function
### Syntax
```
let func = function(){
	console.log("this is expression func");
}
```
### Explain
- Các khai báo như gán giá trị vào biến.
- Được sử dụng kể từ khi nó được khởi tạo.
- Chỉ sử dụng ở phạm vi cục bộ chứ không gọi toàn cục được như declaration function ⇠ Vì các func này được tạo ra khi script tìm đến nó.
```
let age = prompt("What is your age?", 18); 
// conditionally declare a function 
if (age < 18) { 
	function welcome() { alert("Hello!"); 
	} 
} else { 
	function welcome() { alert("Greetings!"); 
	} 
} 
// ...use it later 
welcome(); // Error: welcome is not defined
```
- Vd trong đoạn code trên, vì ``welcome`` chỉ được khai báo bên trong if, nên nếu gọi bên ngoài nó sẽ bị lỗi.
- Không có hoisting.
## *Declaration Function vs Expression Function*
### Declaration
- Là cách khai báo hàm thông thường và có thể được gọi trước khi được định nghĩa (như hoisting).
- Là hàm toàn cục (global function).
- Syntax: const declareFunc (parameter) { ...building block... }
### Expression
- Khai báo thông qua một biểu thức, hoặc gán cho một biến.
- Là hàm có phạm vi sử dụng cục bộ.
- Không có hoisting
- Syntax: let checkFunc = function(){ ...building block... }
## Arrow Function
### Syntax
```
let func = (arg) => {...
	return
}
// note: have to have curly bracket if have return
```
- Cách gọi tương tự như Expression Function
- Nếu xài this.value trong arrow func nó sẽ chỉ ra biến toàn cục bên ngoài arrow func.

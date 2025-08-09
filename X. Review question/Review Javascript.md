1. Sự khác biệt giữa null và undefined trong Js
	→ [[II - 0. Data types]] - Bonus question
2. Sự khác biệt giữa == và ===
	- == chỉ so sánh giá trị, bỏ qua kiểu dữ liệu của biến. VD như so sánh 2 và "2" thì **equal operator** sẽ ép về string để so sánh => 2 & "2" sẽ trả về true
	- === là **strict equal operator**, sẽ so sánh luôn cả giá trị và kiểu dữ liệu của biến. Nên khi so sánh số và chuỗi như 2 & "2" thì sẽ là false. Nó chỉ true khi biến có cùng kiểu dữ liệu và giá trị.
3. Giá trị falsy trong Js
	→ [[II - 0a. Type conversions]] *Falsy value*
4. Declaration Function vs Expression Function
	→ [[II - 6. Functions]] *Declaration Function vs Expression Function*
5. var, let, const cái nào có cơ chế hoisting?
	→ [[II - 7. var, let, const & hoisting]]
6. Value types và Reference types trong Js
	→ [[II - 0b. Value types & Reference types]]
7. What is closure in Js? Provide an example
	A closure is a feature where an inner function has access to outer (enclosing) function's variales.
	```
	function outer(a,b){
		function inner(){
			return (a+b)
		}
		console.log(inner());
	}
	```
8. Explain the different between `.then()` and `async/await`in handling asynchronous operations in JS.
	`.then()` is used with promises for asynchronous operations, chaining multiple calls for sequential execution. `async/await` makes asynchronous code look synchronous and is syntactic sugar over Promises, improving readability and error handling.
9. Describe the lifecycle of a React component and how you would use it to fetch data.
	Answer: [[III - 1. Lifecycle & Props]]
10. Explain event delegation and its advantages
	Read more: https://medium.com/@karthickrajaraja424/explain-event-delegation-in-javascript-and-how-it-improves-performance-1a78cd07986d.
	Event delegation is a technique where instead of adding an event listener to each similar child element, you add a single event listener to a parent element. It leverages the event bubbling phase to catch events from child elements. Advantages include reduced memory usage (fewer event listeners) and dynamically handling events from elements added after the initial page load.
11. 
	






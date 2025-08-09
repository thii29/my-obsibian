1. Thuộc tính data trong HTML được sử dụng để làm gì?
	→ [[I - 0. HTML Data Attribute]]
2. Giải thích về Box Model trong CSS? (Descibe the CSS model and how CSS properties related to it affect layout.)
	→ [[I - 0. CSS Box Model]]
	The CSS box model consists of four areas: content, padding, border, and margin. These layers affect the total size and spacing of an element on the page. Understanding this model is crucial for precise layout control, as it determines how elements are sized and how they interact with each other in the document flow.
3. Sự khác biệt giữa visibility: hidden và display: none là gì?
	- **Giống**: cả hai đều được sử dụng để ẩn đi một phần tử trên trang.
	- **Khác**:
	- `display: none`
		- Phần tử bị ẩn đi và không chiếm không gian sau khi bị ẩn. Nói cách khác là phần tử bị loại bỏ hoàn toàn ra khỏi trang.
		- Không ảnh hưởng đến bố cục trang và các phần tử xung quanh.
	- `visibility: hidden`
		- Phần tử bị ẩn đi nhưng vẫn chiếm không gian trang, chỉ là không được hiển thị. Nói cách khác và phần tử vẫn tồn tại trong layout nhưng không nhìn thấy được và vẫn chiếm diện tích dù bị ẩn.
		- Ảnh hưởng đến bố cục trang và các phần tử xung quanh.
4. How would you implement a design that needs to be responsive across various devices?
	Utilize CSS media queries to apply different styles based on device characteristics like width, height, or orientation. Employ a fluid grid layout and use relative units (em, rem, %) instead of pixels to ensure elements scale proportionally.
5. 
	
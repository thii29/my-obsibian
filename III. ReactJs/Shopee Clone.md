### HTTP Request Method
*References*
- https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods
- https://blog.postman.com/what-are-http-methods/
#### GET
- Sử dụng để lấy dữ liệu trên server hoặc truy cập vào tài nguyên cụ thể. 
- Đặc trưng của Get request ***không bao gồm body*** (http content), nên clients không thể tạo mới hoặc update dữ liệu. Chỉ để đọc dữ liệu.
`GET <request-target>["?"<query>] HTTP/1.1`
#### POST
- Sử dụng để gửi dữ liệu lên, tạo tài nguyên mới trên trên server.
- Đặc trưng của Post request **bao gồm body (http content)**, nơi người dùng chỉ định các thuộc tính tài nguyên được tạo.
- May have additional effects (have side effects)
`POST <request-target>["?"<query>] HTTP/1.1`
#### PUT
- Sử dụng để tạo mới hoặc thay thế (cập nhật) dữ liệu hiện có trên server.
- Tương tự như POST, Put request **bao gồm body (http content)**.
- Put is idempotent (bất biến - gọi bao nhiêu lần thì vẫn vậy) (There are no side effects)
`PUT <request-target>["?"<query>] HTTP/1.1`
#### PATCH
- Sử dụng để cập nhật lại một phần tài nguyên có sẵn, có khái niệm tương tự CRUD, nhưng khác, không nên nhầm lẫn.
- Patch request **bao gồm body (http content)**.
- VD: 1 dữ liệu product có `name`,`brand`,`price` nhưng admin chỉ muốn cập nhật lại giá thì có thể sử dụng PATCH thay vì PUT.
- Can be idempotent, but it is not inherently so. It depends on the nature of the changes being applied and how they are handled by the server.
`PATCH <request-target>["?"<query>] HTTP/1.1`
#### DELETE
- Dùng để loại bỏ dữ liệu (được chỉ định) ra khỏi cơ sở dữ liệu.
`DELETE <request-target>["?"<query>] HTTP/1.1`
### Login & Register Flow
![[login.png]]
![[register.png]]
- Sử dụng [[III - 0c. useContext]] để lưu thông tin user và truyền qua các component khác nhau.
### Show and Find products list
![[productsList.png]]
### Filter and Sort

### Cart 
Url của API backend chứ không phải của sidebar browser
- Thêm vào giỏ hàng
![[add-cart.png]]
- Xoá sản phẩm trong giỏ hàng
- ![[delete product in cart.png]]
### Status code
- Success: thường là hàng 200
- Lỗi frontend (client): thường là hàng 400
- Lỗi server: thường là hàng 500


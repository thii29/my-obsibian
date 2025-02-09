**Syntax:**
```
let promise = new Promise(function(resolve, reject){
	//excutor 
})
```
- Khi promise được tạo ra, đoạn mã bên trong được tự động thực thi. Và khi chạy xong, nó sẽ gọi resolve nếu thành công hoặc reject nếu thất bại. (When a promise is created, the code inside it runs automatically. Once it is completed, it calls `resolve` with a success value; if it fails, it calls `reject`.)
- Lưu ý: resolve, reject là [[II - 3. Callback]] **function**
![[promise.png]]
#### Then, catch
**Then**
*Syntax*:
```
promise.then(
  function(result) { /* handle a successful result */ },
);
```
- Cho phép xích các chuỗi hoạt động bất đồng bộ lại với nhau sau khi "promise resolve". Nó xư lí đầu ra của promise khi hoạt động bất đồng bộ hoàn toàn thành công. (Allows you to chain on additional asynchronous operations after a promise resolves. It handles the outcome of the promise once the asynchronous operation has completed successfully.)
**Catch**
*Syntax*:
```
promise.catch(onReject);
```
- Xử lý các promise bị reject hoặc các lỗi được đưa ra từ chuỗi promise. (It provides a way to handle rejected promises or errors thrown in the promise chain.)

#### Example then & catch
**Scenario**
We'll create a function that simulates checking a user's login status. It will:
1. Return a promise.
2. Resolve if the user is logged in (simulated by a random condition).
3. Reject if the user is not logged in.
```
function checkLoginStatus() {
  return new Promise((resolve, reject) => {
    // Simulate checking login with a timeout
    setTimeout(() => {
      // Simulate a login check by generating a random number
      const isLoggedIn = Math.random() > 0.5;
      if (isLoggedIn) {
        resolve('User is logged in');
      } else {
        reject('User is not logged in');
      }
    }, 1000); // Delay of 1 second
  });
}

// Using the function and handling the promise
checkLoginStatus()
  .then(successMessage => {
    // This block handles the resolved case
    console.log(successMessage);
  })
  .catch(errorMessage => {
    // This block handles the rejected case
    console.error(errorMessage);
  });
```
**Explain**
- Trong đoạn code trên, func `checkLoginStatus` trả về một promise, trong đó:
	- `isLoggedIn` là giả lập trạng thái đăng nhập bằng cách dùng Math.random() (từ 0 đến 1).
	- Nếu `isLoggedIn === true` thì sẽ chạy vào resolver, ngược lại sẽ vào reject.
	- Để hiển thị được kết quả của promise, cần phải sử dụng `.then` & `.catch` để show kết quả thành công hoặc thất bại.
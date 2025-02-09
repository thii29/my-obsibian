### Async function
**Syntax**
```
async function f(){
	return promise.resolve(1)
}
```
- Khi khai báo một hàm bất đồng bộ, thì các thành phần bên trong tự động trả về promise, các thành phần được gói bên trong sẽ tự động xử lý promise.
### Await
**Syntax**
```
let result = await promise
```
- Lưu ý: await chỉ được xài trong async function
- Await không hoạt động với callback
```
async function f() {
  let promise = new Promise((resolve, reject) => {
    setTimeout(() => resolve("done!"), 1000)
  });
let result = await promise; // wait until the promise resolves (*)
  alert(result); // "done!"
}
f();
```
**Lưu ý:** resolve, reject & "() => resolve("done!")" là [[II - 3. Callback]]. Mặc dù thay đổi và update lên nhưng syntax vẫn tương tự như khi gọi callback.
### Error handling
- Tương tự như [[II - 4. Promise]] phải dùng catch, async await phải dùng `try catch` trong trường hợp throws an error & `finally` để kết thúc trạng thái của async await.
```
async function f() {
  await Promise.reject(new Error("Whoops!"));
}

// đoạn trên tương tự đoạn bên dưới

async function f() {
  throw new Error("Whoops!");
}

//Sử dụng try...catch tương tự như throw
async function f() {
  try {
    let response = await fetch('http://no-such-url');
  } catch(err) {
    alert(err); // TypeError: failed to fetch
  }
}
f();
```

##### Summary
The `async` keyword before a function has two effects:
1. Makes it always return a promise.
2. Allows `await` to be used in it.
The `await` keyword before a promise makes JavaScript wait until that promise settles, and then:
1. If it’s an error, an exception is generated — same as if `throw error` were called at that very place.
2. Otherwise, it returns the result.

https://viblo.asia/p/javascript-tu-callbacks-den-promises-va-asyncawait-Do754Jq3ZM6
https://viblo.asia/p/javascript-xu-ly-bat-dong-bo-callbacks-promises-hay-asyncawait-maGK7OaLKj2
https://dev.to/jps27cse/exploring-asynchronous-javascript-callbacks-promises-and-asyncawait-16k6
- Là một hàm có tham số là một hàm khác được truyền vào (It's a function that has another function passed as a parameter).
- Được dùng trong xử lý bất đồng bộ, lưu ý callback vẫn có thể đồng bộ (Used in asynchronous processing, note that callbacks can still be synchronous).
```
function callback() {
  console.log('Hello World')
}
setTimeout(callback, 1000)
// 'callback' truyền vào setTimeout là một callback, nó sẽ được gọi sau 1000 ms 

//Hoặc có thể viết như sau:
setTimeout(()=>{console.log('Hi')}, 2000)

//Another ex:
function loadScript(src, callback) {
  let script = document.createElement('script');
  script.src = src;
  script.onload = () => callback(script);
  document.head.append(script);
}

loadScript('/my/script.js', script => {
  alert(`Cool, the script ${script.src} is loaded`);
  alert( _ ); // _ is a function declared in the loaded script
});
```
#### Handling errors
```
//Có thể viết như này
loadScript('/my/script.js', function(error, script) {
  if (error) {
    // handle error
  } else {
    // script loaded successfully
  }
});

//Thay vì viết:
function callback(error, script) {
  if (error) {
    // handle error
  } else {
    // script loaded successfully
  }
}
loadScript('/my/script.js', callback)
```
#### Callback in callback
Trong ví dụ loadScript, nếu muốn load thêm một đoạn script khác sau khi script số 1 load xong, có thể lồng thêm 1 loadScript vào tron loadScript đầu tiên:
```
loadScript('/my/script.js', function(script) {
  alert(`Cool, the ${script.src} is loaded, let's load one more`);
  loadScript('/my/script2.js', function(script) {
    alert(`Cool, the second script is loaded`);
  });
});
```
#### Pyramid of Doom
Có thể lồng 1 hoặc 2 callback, nhưng nếu có quá nhiều hành động bất đồng bộ lồng vào nhau, đoạn code sẽ như thế này:
```
loadScript('1.js', function(error, script) {
  if (error) {
    handleError(error);
  } else {
    // ...
    loadScript('2.js', function(error, script) {
      if (error) {
        handleError(error);
      } else {
        // ...
        loadScript('3.js', function(error, script) {
          if (error) {
            handleError(error);
          } else {
            // ...continue after all scripts are loaded (*)
          }
        });
      }
    });
  }
});
```
- Đoạn code bị lồng quá nhiều và gọi callback sâu hơn sẽ dẫn tới "callback hell" hoặc "pyramid of doom" (Many callbacks are nested, leading to deeper callback levels, which can result in callback hell or the pyramid of doom).
- Để giảm bớt vấn đề này, nên viết lại đoạn code như sau:
```
loadScript('1.js', step1);

function step1(error, script) {
  if (error) {
    handleError(error);
  } else {
    // ...
    loadScript('2.js', step2);
  }
}

function step2(error, script) {
  if (error) {
    handleError(error);
  } else {
    // ...
    loadScript('3.js', step3);
  }
}

function step3(error, script) {
  if (error) {
    handleError(error);
  } else {
    // ...continue after all scripts are loaded (*)
  }
}
```

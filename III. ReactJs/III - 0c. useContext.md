**Syntax**
`const value = useContext(SomeContext)`
- SomeContext đã được tạo trước đó với `createContext`
`const SomeContext = createContext(defaultValue)`
`SomeContext.Provider` || `SomeContext.Consumer`
SomeContext.Provider: Sẽ được bao trên cùng của các component
![[useContext.jpg]]

**Explain**
- Xác định giá trị context: trả về giá trị từ provider gần nhất của "`SomeContext` nằm trên cùng của cây component". Nếu không có provider nào, giá trị trả về sẽ là `defaultValue` khi tạo context bằng createContext.
- React tự động re-render component sử dụng `useContext`để luôn cập nhật giá trị gửi về.

**Return**
- Giá trị context được cung cấp bởi `SomeContext.Provider`, hoặc giá trị mặc định `defaultValue` khi khởi tạo bằng `createContext` 

**Usage**
- Truyền dữ liệu từ component cha vào các component con sâu dưới cây mà không cần thông qua props.
- Cập nhật dữ liệu được truyền thông qua context.
- Chỉ định mặc định giá trị dự phòng.
- Ghi đè context cho một phần của cây (Overriding context for a part of the tree).
	-  You can override the context for a part of the tree by wrapping that part in a provider with a different value.
	- You can nest and override providers as many times as you need.
```
<ThemeContext.Provider value="dark">  
...  
	<ThemeContext.Provider value="light">  
		<Footer />  
	</ThemeContext.Provider>  
...  
</ThemeContext.Provider>
```
- Tối ưu hoá lại hiển thi khi truyền qua objects và function.
	- You can pass any values via context, including objects and functions.
```
function MyApp() {  

const [currentUser, setCurrentUser] = useState(null);  
  
function login(response) {  
	storeCredentials(response.credentials);  
	setCurrentUser(response.user);  

}  

return (  
	<AuthContext.Provider value={{ currentUser, login }}>  
		<Page />  
	</AuthContext.Provider>  
	);  
}
```
**Example**
```
import { createContext, useContext, useState } from 'react';

const ThemeContext = createContext(null);
//khởi tạo context, default value là null

export default function MyApp() {
  const [theme, setTheme] = useState('light');
  return (
    <ThemeContext.Provider value={theme}>
    //Provider đang bao Form
      <Form />
      <label>
        <input
          type="checkbox"
          checked={theme === 'dark'}
          onChange={(e) => {
            setTheme(e.target.checked ? 'dark' : 'light')
          }}
        />
        Use dark mode
      </label>
    </ThemeContext.Provider>
  )
}

function Form({ children }) {
//children là props ko cần truyền, chỉ dùng để xách định xài //chức năng ở đâu trong phần con.
  return (
    <Panel title="Welcome">
      <Button>Sign up</Button>
      <Button>Log in</Button>
    </Panel>
  );
}

function Panel({ title, children }) {
  const theme = useContext(ThemeContext);
  const className = 'panel-' + theme;
  return (
    <section className={className}>
      <h1>{title}</h1>
      {children}
    </section>
  )
}

function Button({ children }) {
  const theme = useContext(ThemeContext);
  const className = 'button-' + theme;
  return (
    <button className={className}>
      {children}
    </button>
  );
}
```



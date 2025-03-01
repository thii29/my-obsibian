**Reference link:** https://200lab.io/blog/huong-dan-su-dung-zustand-trong-nextjs
**Document: ** https://zustand.docs.pmnd.rs/getting-started/introduction
### Zustand là gì? / What is Zustand?
- Là 1 thư viện quản lý trạng thái nhẹ cho React.
- Cung cấp 1 API đơn giản, linh hoạt & hiệu suất cao giúp quản lý state dễ dàng mà không cần viết nhiều code phức tạp. (Zustand has a comfy AAPI based on hooks)

### Installation
`npm install zustand` or `yarn add zustand`

### Guide
#### Basic useage
Create a store
```
import { create } from 'zustand'

interface BearState {
  bears: number;
  increase: (by: number) => void;
}
const useBearStore = create<BearState>()((set) => ({
  bears: 0,
  increase: () => set((state) => {state.bears + 1}),
}))

export default useBearStore
```

Use in component(s)
```
import useBearStore from '../hooks/useBearStore'

const HomePage: React.FC = () =>{
	const countIncrease = useBearStore((state)=> state.countIncrease)
	return(
		<h4>{countIncrease} bears around here...</h4>
	)
}
```

**Vì sao zustand không cần wrap provider như redux hay context**
- API dựa trên hook: sử dụng hooks để tạo & sử dụng kho trạng thái. Nhờ vào hooks, các thành phần React có thể trực tiếp truy cập & đăng ký với trạng thái cần thiết mà không cần thông quâ Context Provider -> giảm bớt sự phức tạp trong cấu trúc ứng dụng.
- Truy cập trực tiếp & tái sử dụng: cho phép các component truy cập trực tiếp đến kho trạng thái mà không cần thông qua provider -> giải thiểu số lượng wrapping không cân thiết & cho phép tái sử dụng các kho trạng thái dễ dàng hơn giữa các thành phần khác nhau.
- Hiệu suất & đơn giản: không sử dụng provider giúp giảm thiểu re-renders không cần thiết->tối ưu hoá hiệu suất & đơn giản hoá luồng dữ liệu trong ứng dụng.
- Quản lý trạng thái tập trung: duy trì kho trạng thái tập trung mà tất cả component có thể truy cập-> quản lý trạng thái nhất quán.
*Vd từ ChatGPT*
Dưới đây là các ví dụ minh họa cho các điểm bạn yêu cầu:

### 2. Truy cập Trực tiếp và Tái sử dụng

Giả sử chúng ta có một kho trạng thái Zustand dùng chung cho toàn bộ ứng dụng để quản lý thông tin người dùng:

```javascript
import create from 'zustand';

const useUserStore = create(set => ({
  user: null,
  setUser: user => set({ user })
}));

function ProfileComponent() {
  const { user, setUser } = useUserStore();
  return (
    <div>
      <h1>User Profile</h1>
      <p>Name: {user ? user.name : "No user"}</p>
      <button onClick={() => setUser({ name: "Nguyen Quoc Vuong" })}>Set User</button>
    </div>
  );
}
```

Trong ví dụ này, `useUserStore` là một hook cho phép các thành phần khác nhau truy cập và cập nhật trạng thái người dùng mà không cần bất kỳ provider nào. Kho trạng thái này có thể được sử dụng lại ở bất cứ đâu trong ứng dụng.

### 3. Hiệu suất và Đơn giản

Khi bạn chỉ cần một phần của trạng thái, Zustand chỉ gây ra tái hiển thị cho các thành phần sử dụng phần đó:

```javascript
function CounterComponent() {
  const count = useUserStore(state => state.count);
  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={() => useUserStore.setState(prevState => ({ count: prevState.count + 1 }))}>
        Increment
      </button>
    </div>
  );
}
```

Trong ví dụ này, chỉ có `CounterComponent` sẽ tái hiển thị khi `count` thay đổi, mà không ảnh hưởng đến các thành phần khác sử dụng kho trạng thái này, giúp cải thiện hiệu suất.

### 4. Quản lý trạng thái tập trung

Mặc dù không dùng provider, Zustand vẫn quản lý trạng thái tập trung:

```javascript
// Chia sẻ trạng thái giữa các thành phần
function DisplayUserComponent() {
  const user = useUserStore(state => state.user);
  return <p>Logged in as: {user ? user.name : "Guest"}</p>;
}
```

Cả `ProfileComponent` và `DisplayUserComponent` có thể truy cập và cập nhật `user` mà không cần thông qua provider, đảm bảo trạng thái được quản lý một cách nhất quán và dễ dàng chia sẻ giữa các thành phần.

**Should read:** https://medium.com/globant/react-state-management-b0c81e0cbbf3


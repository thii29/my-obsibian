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


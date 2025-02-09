### What are React Hooks? (React Hooks là gì?)
- Là một tính năng trong thư viện React (từ phiên bản 16.8) giúp sử dụng các functional components thay vì class component.
- Hooks giúp quản lý state (trạng thái), hiệu suất và vòng đời của các component dễ dàng hơn.
### How is React Hook different from React Class? (React Hook khác React Class như thế nào?)
- Khác nhau về syntax:
	- React class: 
	```
	export default class Example extends React.Componen{
	.... render (){
		return (...)
		}
	}
	```
	- React hook: 
```
export default function Example(){
	  ...
	  return ()
}
```
- React class là về hướng đối tượng, còn reack hooks là hướng chức năng.
- Sử dụng state:
	- React class khởi tạo state trong constructor và truy cập thông qua this.state.
	- React hooks sử dụng useState để quản lý state functional component.
- Lifecycle methods:
	- React class cung cấp method như `componentDidMount`, `componentDidUpdate` và `componentWillUnmount`.
	- React hooks sử dụng useEffect để xử lý lifecycle trong functional component.

### Tại sao cần sử dụng Hooks ?
- Trước khi có Hooks, state, life cycle cuar component được quản lý trong class components, functional component không có khả năng quản lý này → **Quản lý state & life cycle của component dễ dàng hơn**
- Class component sẽ trở nên phức tạp hơn khi quản lý nhiều life cycle & state khác nhau → **Giảm sự phức tạp bằng cách sử dụng các hook riêng lẻ để quản lý từng component**
- **Tối ưu hoá việc render component thông qua useMemo, useCallback & các hooks khác**
- **Tái sử dụng logic và trạng thái**
### State Hooks
- [[III - 0a. useState]]
- useReducer
### Context Hooks
- [[III - 0c. useContext]]
### Ref Hooks
- useRef
### Effect Hooks
- useEffect
- useLayoutEffect
### Performance Hooks
- [[III - 0g. useCallback]]
- [[III - 0h. useMemo]]

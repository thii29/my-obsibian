**Syntax**
```
const cachedFn = useCallback(fn, dependencies)
```
**Explain**
In other words, `useCallback` caches a function between re-renders until its dependencies change.

**Usage**
- Tránh render lại các component không cần thiết.
- Updating state from a memorized callback.
	- Sometimes, we might need to update new state based on previous state from memorized callback. You might initially include the state variable as a dependency in the callback such as an example below:
	```
	function TodoList() {  
		const [todos, setTodos] = useState([]);  
	
		const handleAddTodo = useCallback((text) => {  
			const newTodo = { id: nextId++, text };  
			setTodos([...todos, newTodo]);  
		}, [todos]); 

	```
	- To **optimize and reduce dependencies**, React allows to use an updater function with the state setter function (`setTodos`). The updater function receives the previous state as its parameter and returns the new state
	```
	function TodoList() {
	  const [todos, setTodos] = useState([]);

	  const handleAddTodo = useCallback((text) => {
	    const newTodo = { id: nextId++, text };
	    setTodos(prevTodos => [...prevTodos, newTodo]);
	  }, []);  // No dependency on todos
	}
	```
- Preventing an Effect from firing too often (debouncing or throttling).
- Tối ưu hoá hook điều chỉnh.

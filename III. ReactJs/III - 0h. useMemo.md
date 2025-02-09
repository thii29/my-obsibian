**Syntax**
```
const cachedValue = useMemo(calculateValue, dependencies)
```
**Explain**
- Let you cache the result of a calculation between re-renders. (Ghi nhớ lại kết quả của một hàm cho đến khi dependencies thay đổi.)
- calculateValue is the function calculating, it should be pure, no arguments and should return a value of any type.
- Return ==an already stored value from the last render== (if the dependencies haven’t changed), or call `calculateValue` again, and return the result that `calculateValue` has returned.

**Usage**
- Tránh việc tính toán lại giá trị tốn kém mỗi khi component re-render.
- Preventing an Effect from firing too often.
- Memoizing a dependency of another Hook.
- Memoizing a function.
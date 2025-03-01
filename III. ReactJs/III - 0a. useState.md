ex: `const [state, setState] = useState(initialState)`
//initialState có thể bỏ qua và chỉ dùng cho lần đầu

**State**  
- State of a component is an object that holds some informations, data that can may change over the lifetime of the component. It can keep the data when rendering.
- Quản lý giá trị trong component. Lưu trữ, dữ lại data khi render

**useState trả về cái gì?**
- State hiện tại
- Thiết lập hàm dùng để cập nhật state với giá trị khác và kích hoạt re-render

**Lưu ý:**
- Không thể sử dụng trong vòng lặp.
- Là hàm bất đồng bộ.

VD: hàm  handleIncrease()  bên dưới, dù cho bên trong có bao nhiêu setCounter bên trong thì nó vẫn chỉ thay đổi 1 lần cho đến lần render tiếp theo.
```
const [counter, setCounter] = useState(1);
function handleIncrease() {
  setCounter(counter + 1);
  setCounter(counter + 1);
  setCounter(counter + 1);
  setCounter(counter + 1);
}
```

- Mỗi state là độc lập, không liên quan đến nhau. Nó chỉ được thay đổi khi render lại
*Component sẽ được render lại sau khi setState*


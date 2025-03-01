## Lifecycle
Mỗi một component trong ReactJs đều có lifecycle riêng gồm có 4 trạng thái.
**Khởi tạo (initial)**
**Mounting**
**Updatiing**
**Unmounting**

## Props
- Props are a way to pass data from parent components to child components.
- Props are read-only, that mean a component can only read the props given to it from its parents component and cannot modify or change them.
- Props are central to component communication.
### Key futures
- **Immutability**: Props are immutable within the component that receives them, which means you cannot change their values directly.
- **Data Flow**: Props allow for a one-way data flow from parent to child component, which aligns with React's unidirectional data flow model. This makes the data flow predictable and easier to understand.
- **Flexibility**: They can be used to pass various types of data, including numbers, strings, functions, arrays, and even other React components.
- **Reusability**: By using props, components can be made more generic, thus more reusable. Different values of props can be passed to the same component to render different results.
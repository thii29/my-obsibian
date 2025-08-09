1. What are the major features of React? 
	- It uses **VirtualDOM** instead of **RealDOM**, which means it only updates parts of the web page that need to change, not the whole page. This boosts performance and makes things faster.
	- React uses a one-way data flow, which means information moves in just one direction. This approach makes the data easier to track and reduces errors related to data updates.
	- You can reuse components and put them together to create complex web pages. This makes coding more organized and easier to handle.
	- **Hooks** is a feature from version 16.8 that supports using state and other React features in functional components without needing to write a class.
	- Supports **server-side rendering**. (You can install some packages for this feature.)
2. What is JSX? (JSX là gì?)
	- Stand for JavaScript XML. 
	- It's a syntax extension for JavaScript, primarily used with React. 
	- JSX allows developers to write HTML-like code directly within JS code.
3. What is state in React? 
	[[III - 0a. useState]]  part **State**
7. What are props in React?
	[[III - 1. Lifecycle & Props]] part **Props**
8. What is the different between state and props?

| Feature               | Props                              | State                             |
|-----------------------|------------------------------------|-----------------------------------|
| **Definition**        | Data passed from parent to child   | Data managed within the component |
| **Mutability**        | Read-only and immutable            | Mutable and can be updated        |
| **Control**           | Controlled by parent component     | Controlled by the component itself|
| **Purpose**           | Pass data and event handlers to components | Handle data that changes over time  |
| **Triggers Re-render**| Yes, when changes occur            | Yes, when updated                 |
| **Access**            | Can be accessed by the child component | Private to the component         |
| **Usage**             | Ideal for configuring components and passing static data | Used for interactive or dynamic UI parts |

In React, components utilize props and state to manage data. Props are data passed from a parent component to a child component. They are immutable, meaning they cannot be modified by the child component, and are controlled by the parent component. This allows the child component to access the data provided by its parent. On the other hand, the state is data that is managed within the component itself. It is mutable, meaning it can be updated, and it is controlled exclusively by the component that owns it, making it private to that component. This distinction highlights how props and state function in React.
1. React Hooks là gì? (What are React Hooks?)
	→ [[III - 0. React Hooks]]
10. React Hook khác gì với React Class? (How is React Hook different from React Class?)
	→ [[III - 0. React Hooks]]
11. useCallback có ưu điểm gì?
	→ [[III - 0g. useCallback]]
12. Tại sao cần sử dụng [[React-Hook-Form]]
	→ Hiệu suất tối ưu: giảm số lượng re-renders khi người dùng gõ vào các trường biểu mẫu → nhập liệu nhanh hơn, ít tốn tài nguyên hơn.
	→ Dễ dàng tích hợp
	→ Validation ease
	→ Tương thích tốt: hỗ trợ các thư viện phổ bién như Material-UI, Ant design, Chakra UI,...
	→ Hỗ trợ Typescript
13. What is the difference between HTML and React event handling?

| Feature                   | HTML                                          | React                                      |
|---------------------------|-----------------------------------------------|--------------------------------------------|
| **Event Naming**          | Lowercase (e.g., `onclick`)                   | CamelCase (e.g., `onClick`)                |
| **Handler Assignment**    | Directly in HTML attributes                   | Passed as props in JSX                     |
| **Context of `this`**     | Refers to the element (unless bound)          | Must bind in class components              |
| **Event Persistence**     | Events persist naturally                      | Synthetic events are pooled (use `event.persist()` if needed) |
| **Performance**           | Direct attachment can impact performance      | Uses event delegation at root for better performance |
| **Cross-Browser Support** | Requires handling browser inconsistencies     | Normalizes events across browsers          |

1. Describe the lifecycle of a React component and how you would use it to fetch data
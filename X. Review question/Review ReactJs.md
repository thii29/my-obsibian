1. What is React? (React là gì?)
	React is an open-source front-end JavaScript library that is used for building user interfaces, especially for single-page applications. It is used for handling view layer for web and mobile apps.
2. What are the major features of React? 
	- It uses **VirtualDOM** instead of **RealDOM**, which means it only updates parts of the web page that need to change, not the whole page. This boosts performance and makes things faster.
	- React uses a one-way data flow, which means information moves in just one direction. This approach makes the data easier to track and reduces errors related to data updates.
	- You can reuse components and put them together to create complex web pages. This makes coding more organized and easier to handle.
	- **Hooks** is a feature from version 16.8 that supports using state and other React features in functional components without needing to write a class.
	- Supports **server-side rendering**. (You can install some packages for this feature.)
3. What is JSX? (JSX là gì?)
	- Stand for JavaScript XML. 
	- It's a syntax extension for JavaScript, primarily used with React. 
	- JSX allows developers to write HTML-like code directly within JS code.
	- Makes the structure of component's UI easier to understand and maintain, as it  binds HTML structure & JS logic in a single file.
4. What is the difference between Element and Component? (Sự khác nhau giữa Element & Component?)
	- React Element:
		- A plain object that desscribes what to appear on screen, like a blueprint.
		- Cannot contain logic or state, simply represents a node or a tree of nodes in the DOM
		- Elements are immutable and cannot change after created.
	- React Component:
		- A function or a class that returns a React Element.
		- Can contain logic, state, lifecycle methods, and can rturn multiple elements via JSX.
		- Components can manage state and update dynamically.
5. How many ways to create components in React?
	- Functional Components: are simpler and more modern in the React ecosystem. They're basically Javascript functions that return JSX, which describes the UI.
	- Class Components: are more traditional and use ES6 classes. They are suitable for more complex components, espcially when dealing with more extensive logiv and state management.
6. What is state in React? 
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

9. React Hooks là gì? (What are React Hooks?)
	→ [[III - 0. React Hooks]]
10. React Hook khác gì với React Class? (How is React Hook different from React Class?)
	→ [[III - 0. React Hooks]]
11. useCallback có ưu điểm gì?
	→ [[III - 0g. useCallback]]
12. Tại sao cần sử dụng [[React-Hook-Form]]
	→ Hiệu suất tối ưu: giảm số lượng re-rendế khi người dùng gõ vào các trường biểu mẫu → nhập liệu nhanh hơn, ít tốn tài nguyên hơn.
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


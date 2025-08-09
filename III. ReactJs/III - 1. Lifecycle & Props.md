## Lifecycle
Mỗi một component trong ReactJs đều có lifecycle riêng gồm có 4 trạng thái.
**Khởi tạo (initial)**
**1. Mounting**
- The component is rendered to the DOM for the first time.
- This is a good moment to initiate data fetching because you want the data to be ready as soon as your component is displayed.
Example fetching data on mount
```
import React, { useState, useEffect } from 'react';

function FetchOnMount() {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => setData(data))
      .catch(error => console.error('Error fetching data:', error));
  }, []);  // Empty dependency array means this runs only on mount 
  //only run once time

  return (
    <div>
      {data ? <pre>{JSON.stringify(data, null, 2)}</pre> : 'Loading...'}
    </div>
  );
}

```
If doesn't have dependencies, useEffect() always run and doesn't care about which state is updating.
**2. Updating**
- Occurs when component state or props change.
- If your data fetch depends on props or state (like a user ID or a search query), you might need to fetch new data when these dependencies change.
Example updating based on dependency changes
```
import React, { useState, useEffect } from 'react';

function CounterEffect({ count }) {
  useEffect(() => {
    // This code runs when 'count' changes
    console.log(`Count has changed to: ${count}`);
  }, [count]);  // This effect depends on 'count'

  return (
    <h1>{count}</h1>
  );
}

```
**3. Unmounting**
- The component is being removed from the DOM.
- This phase is less about fetching data and more about cleaning up any ongoing processes that shouldn’t continue once the component is gone (like canceling unfinished network requests).
Example setting up and cleaning up an interval
```
import React, { useState, useEffect } from 'react';

function TimerComponent() {
  const [seconds, setSeconds] = useState(0);

  useEffect(() => {
    const intervalId = setInterval(() => {
      setSeconds(prevSeconds => prevSeconds + 1);
    }, 1000);

    // Cleanup function
    return () => {
      clearInterval(intervalId);
      console.log('Timer cleanup');
    };
  }, []);  // Empty array means the effect runs only on mount and cleanup on unmount

  return (
    <div>Seconds: {seconds}</div>
  );
}
```
### Explanation:
- **Mounting Example:** The `useEffect` with an empty dependency array acts like `componentDidMount` as it runs only once after the initial render.
- **Updating Example:** By specifying `count` in the dependency array, the effect acts like `componentDidUpdate`, where it only runs when `count` changes.
- **Unmounting Example:** The return function in `useEffect` is the cleanup phase, equivalent to `componentWillUnmount`. It's used to clear resources, like clearing timers or unsubscribing from services to prevent memory leaks.

## Props
- Props are a way to pass data from parent components to child components.
- Props are read-only, that mean a component can only read the props given to it from its parents component and cannot modify or change them.
- Props are central to component communication.
### Key futures
- **Immutability**: Props are immutable within the component that receives them, which means you cannot change their values directly.
- **Data Flow**: Props allow for a one-way data flow from parent to child component, which aligns with React's unidirectional data flow model. This makes the data flow predictable and easier to understand.
- **Flexibility**: They can be used to pass various types of data, including numbers, strings, functions, arrays, and even other React components.
- **Reusability**: By using props, components can be made more generic, thus more reusable. Different values of props can be passed to the same component to render different results.
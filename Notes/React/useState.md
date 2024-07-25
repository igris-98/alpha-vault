# useState:
- Creating State:
	```jsx
	// simple
	const [count, setCount] = useState(20);

	// Based on function (lazy evaluation)
	// Function must be pure and accept no arguments. Called only on initial render.
	const [count, setCount] = useState(() => localStorage.getItem('count'));
	```
- Updating State:
	```jsx
	// simple
	setCount(1000);

	// based on current state
	// Function must be pure and return next state
	setCount((current) => current + 1);
	```

#NOTE/REACT/STATE
- When Updating state, make sure to NOT mutate objects or arrays, but to replace them with new one.

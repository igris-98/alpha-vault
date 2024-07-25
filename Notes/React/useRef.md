# useRef:
- We use the useRef hook to create something called a **ref**. 
- Ref stands for reference. It's like a box into which we can put any data that we want to be **preserved** between renders.
- When we use `useRef`, React will give us an **object** with a **mutable current** property. Then we can write any data into this current property and also read from it.

```jsx
const myRef = useRef(23);

// Refs are presisted across renders.
myRef.current = 1000;
```


## use cases:
- Creating a variable that stays the same between renders. ( previous state, setTimeout id, etc.)
- selecting or store DOM Elements.

#NOTE/REACT/REFS
- Refs are for **data that is NOT rendered**: usually only appear in event handlers or effects, not in JSX ( otherwise use state).
- YOU ARE NOT ALLOW to READ or WRITE the current property in render logic. That would create an undesirable side effect.
- Updated synchronously.

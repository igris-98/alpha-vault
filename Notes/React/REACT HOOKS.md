# React Hooks:
- Special built-in functions that allow us to 'hook' into React Internals.
- Hooks are basically APIs that expose some internal React functionality.
	- Creating or Accessing **state** from Fiber tree.
	- Registering side effects in the fiber tree.
	- Manual DOM selections. etc.
- Always start with `use` like `useState`, `useEffect`.

## The Rules of Hooks:
- **Only call hooks at the top level.**
	- Do not call hooks inside **conditional**, **loops**, **nested functions** or after an **early return**.
	- This is necessary to ensure that hooks are always called in the **same order** (hooks rely on this).
- **Only call hooks from React Functions** 
	- **Only call** hooks inside a **function component** or a **custom hook**.
	- **Not called** from **regular functions** or even **class component**.

## Built-in Hooks:
- [[useState]]
- [[useEffect]]
- [[useReducer]]
- [[useContext]]
- [[useRef]]
- [[useCallback]]
- [[useMemo]]
- [[useTransition]]
- [[useDeferredValue]]

- [[useLayoutEffect]]
- [[useDebugValue]]
- [[useImperativeHandle]]
- [[useId]]

- [[useSyncExternalStore]]
- [[useInsertionEffect]]


#NOTE/REACT/FIBER-TREE
The Fiber Tree is somewhere deep inside React and usually not accessible to us at all. But using hooks, we can essentially hook into that internal mechanism.
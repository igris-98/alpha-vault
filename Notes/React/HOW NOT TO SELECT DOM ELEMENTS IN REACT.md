# How NOT to SELECT DOM Elements in REACT :
```jsx
function Search() {
	useEffect(function(){
		// manually selecting a dom element is not really a react way of doing things
		const el = document.querySelector(".search");
		el.focus();
	},[])
	return <input type="text" className="search" />
}
```

Solution: To make the action of selecting an elements more declarative such as everything else in React, we use concepts of refs.
[[useRef]]
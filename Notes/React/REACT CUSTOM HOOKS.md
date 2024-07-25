# React Custom Hooks
- Custom hooks are all about re-usability.
- Allow us to re-use non-visual logic in multiple components.
- One custom hook should have **one purpose**, to make it **reusable** and **portable**( even across multiple projects).

# Create a custom hook:
- Function name needs to start with `use`.
- Custom hooks needs to use one or more hooks.
- Custom hook can receive and return any relevant data (usually `[]` or `{}`).

```jsx
function useFetch(url){
	const [data, setData] = useState([]);
	const [isLoading, setIsLoading] = useState(false);

	useEffect(function(){
		fetch(url).then((res) => res.json()).then((res) => setData(res));
	},[]);

	return [data, isLoading]; // return as [] or {}.
}
```
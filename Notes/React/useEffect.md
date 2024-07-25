[[REACT]]
prerequisite : [[COMPONENT INSTANCE LIFE CYCLE]]

# useEffect:
- useEffect is like an event listener that is listening for one dependency to change. Whenever a dependency changes, it will execute the effect again.
- useEffect is a **synchronization** mechanism. component's state/props synchronize with external system(side effect).
- effects react to updates to state and props used inside the effect(the dependencies). So effects are **reactive**.
- Each effect should do **only on thing**. Use one useEffect hook for each side effect. This makes effect easier to clean up.

## How Should we fetch data in react:
```jsx
import { useState, useEffect } from react;
function App(){
	const [movies, setMovies] = useState('');

	useEffect(function(){
		fetch(url).then((raw) => raw.json()).then((data) => setMovies(data));
	}, []);

	return <>
		movies.map(item => (
			<div key={item.id}> item.movie_name </div>
		))
	</>
}
```

## Dependency Array:
- By default, effects run **after every render**. we can prevent that by passing a **dependency array**.
- Without the dependency array, React doesn't know **when** to run the effect.
- Each Time one of the dependency changes, the effect will be executed again.
- Every state variable and prop used inside the effect **MUST** be included in the dependency array. Otherwise we get a **stale closure**.
	```jsx
	const [title, setTitle] = useState();
	const [userRating, setUserRating] = useState();
	
	useEffect(
		function(){
			if(!title) return;
			document.title = `${title} ${userRating}`;
		},
		[title, userRating]
	);
	
	```


## Synchronization and Lifecycle:
```jsx
useEffect(fn, [x,y,z]); // effect synchronizes with x,y,z // runs on mounted and re-renders triggered by updating x,y,z.
useEffect(fn, []); // effect synchronizes with no state/props // runs only on  mounted (initial render).
useEffect(fn); // effect synchronizes with everything // runs only every render. 
```


## When are effects executed?
- Only executed after browser painted.
- useLayoutEffect is executed before browser painted. React Team discourage this hook.


## useEffect cleanup function:
- Function that we can return form an effect(OPTIONAL).
- Runs on two different occasion:
	- Before the effect is executed again.
	- After a component instance has unmounted.
```jsx
useEffect(function(){
// statement;
return function(){}
}, [])
```
- Necessary whenever the side effect keeps happening after the component has been re-rendered or unmounted.
	- HTTP request -> cancel request
	- API subscription -> cancel subscription
	- start timer -> stop timer
	- add event listener -> remove even listener
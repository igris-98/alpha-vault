[[REACT]]
# How not to fetch data in react:
```jsx
import { useState } from react;
function App(){
	const [movies, setMovies] = useState('');


	// NOT ALLOWED IN RENDER LOGIC 
	// Produce a side effect and always again and again because component needs to be re-rendered due to state is updated.
	// NEVER DO THAT INSTEAD USE useEffect();
	fetch(url).then((raw) => raw.json()).then((data) => setMovies(data));


	return <>
		movies.map(item => (
			<div key={item.id}> item.movie_name </div>
		))
	</>
}
```

SOLUTION: use [[useEffect]] Hook.
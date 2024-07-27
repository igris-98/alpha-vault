# HTTP Module:

```js
const http = require('http'):

const server = http.createServer((request,response) => {
	const pathname = req.url;
	res.end('Hello from the server');
});

// listen(PORT, HOST(optional), callback);
server.listen(3000,'127.0.0.1', ()=>{
	console.log("server listen to port 3000");
});
```
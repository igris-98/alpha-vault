# FS Module:
- This module used for reading data from files and writing data into files.

```js
const fs = require('fs'); // commonJS

const data = fs.readFileSync(path_to_file,utf-8);// block the thread
fs.readFile(path_to_file,utf-8,(err, data)=>{
	console.log(data);
});// not block the thread
```
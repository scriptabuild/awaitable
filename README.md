# awaitable

Utility to turn a nodejs style asyncronous function (ie. one that
takes a function(err, result) callback parameter) into a function
that returns a promise instead. (Since such functions can be await'ed.)

Example:
```javascript
let fileContents = await awaitable(cb => fs.readFile(file, options, cb);
```

Example creating an async function:
```javascript
async function readFile(file, options) {
	return awaitable(cb => fs.readFile(file, options, cb));
}

let fileContents = await readFile(file, options);
```

Example creating an async lambda expression:
```javascript
let readFile = async(file, options) => awaitable(cb => fs.readFile(file, options, cb);

let fileContents = await readFile(file, options);
```

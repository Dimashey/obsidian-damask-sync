In Node.js, reading large files can be handled efficiently by using **streams** rather than loading the entire file into memory at once. Streams **allow you to process large files in chunk**s, which saves memory and improves performance, especially when dealing with very large files.

## Using streams

```js
const fs = require('fs');

// Create a readable stream
const stream = fs.createReadStream('largefile.txt', { encoding: 'utf8', highWaterMark: 16 * 1024 }); // 16 KB chunks

// Handle data event for each chunk
stream.on('data', (chunk) => {
  console.log(`Received chunk of size: ${chunk.length}`);
  // You can process the chunk here
});

// Handle error event in case something goes wrong
stream.on('error', (err) => {
  console.error(`Error reading file: ${err}`);
});

// Handle end event when the stream finishes reading the file
stream.on('end', () => {
  console.log('Finished reading the file');
});
```


## Using `fs.readFile()` (Not Efficient for Large Files)

The `fs.readFile()` method reads the **entire file into memory at once**. While this is easy to use for small or medium-sized files, it is not suitable for large files as it can cause high memory usage.

```js
const fs = require('fs');

fs.readFile('largefile.txt', 'utf8', (err, data) => {
  if (err) throw err;
  console.log(data); // Data contains the entire file content
});
```

## Using `readline` Module (Line-by-Line Reading)

If you need to process a file line-by-line (e.g., for large log files), the `readline` module can be combined with streams to efficiently read files without loading the entire file into memory.

```js
const fs = require('fs');
const readline = require('readline');

// Create a readable stream for the file
const fileStream = fs.createReadStream('largefile.txt');

// Create a readline interface
const rl = readline.createInterface({
  input: fileStream,
  crlfDelay: Infinity
});

// Read the file line-by-line
rl.on('line', (line) => {
  console.log(`Line from file: ${line}`);
});

// Handle when reading is done
rl.on('close', () => {
  console.log('Finished reading the file');
});
```

References:
1. [[Node js]]
2. [[Node js main components]]

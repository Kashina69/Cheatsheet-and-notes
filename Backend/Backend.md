# 1 Import Export

- ## Import Common js

```js
const variableName = require("module");
```

- ## Export Common js

```js
module.exports = component OR Function ;
```

- ## Import ECMA js

```js
import function from ecma
```

- ## Export Common js

```js
export default ecma;
```

# 2 Events

```js
const EventEmitter = require("events");
const myEmitter = new EventEmitter();

myEmitter.on("start", () => {
  console.log("Start event received. Running task...");
  setTimeout(() => {
    console.log("Task complete!");
    myEmitter.emit("finish");
  }, 3000);
});

myEmitter.on("finish", () => {
  console.log("Finish event received. Continuing...");
});

myEmitter.emit("start");
console.log("Application still running...");

```

# 3 Read file and directory using the FS module

- ## Read Directory

```js
const fs = require("fs");
fs.readdir(__dirname, (err, files) => {
  if (err) {
    console.error("Error reading directory:", err);
  } else {
    console.log("Files in the directory:", files);
  }
});
```

- ## Async Read Directory

```js
try {
  const files = fs.readdirSync(__dirname);
  files.forEach((file) => {
    console.log(file);
  });
} catch (err) {
  console.error("Error reading directory:", err);
}
```

- ## Read File

```js
fs.readFile("fileName.txt", "utf-8", (error, data) => {
  if (error) {
    console.error("Error reading file:", error);
  } else {
    console.log("File content:", data);
  }
});
```

- ## Read File Async

```js
try {
  const fileData = fs.readFileSync(filePath, "utf-8");
  console.log("File content (sync):", fileData);
} catch (err) {
  console.error("Error reading file (sync):", err);
}
```

- ## Write File

```js
fs.writeFile(filePath, contentToWrite, (err) => {
  if (err) {
    console.error("Error writing file:", err);
  } else {
    console.log("File has been written.");
  }
});
```

# 4 HTTP Server Setup

```javascript
const http = require("http");
const PORT = process.env.PORT || 3000;

const server = http.createServer((req, res) => {
  res.writeHead(200, { "Content-Type": "text/html" });
  res.write('<html><body><h1>Hello, World!</h1></body></html>');
  res.end();
});

server.listen(PORT, () => {
  console.log(`Server listening on port ${PORT}`);
});

```



# 5 Lodash

```javascript
const _ = require("lodash");

console.log(_.random(0, 20));

const greet = _.once(() => {
  console.log("This function will only run once.");
});

greet();
greet();

```

# 6 Streams

```javascript
const fs = require("fs");

const readStream = fs.createReadStream("file.txt", { encoding: "utf-8" });
const writeStream = fs.createWriteStream("output.txt");

readStream.on("data", (chunkOfData) => {
  console.log("-- New chunk of data ----");
  console.log(chunkOfData);
  console.log(chunkOfData.toString());
  writeStream.write(chunkOfData);
});

readStream.pipe(writeStream);
```

# 7 ENV variables

```js
require("dotenv").config();
process.env.APIKEY;
```


# 8 Code splitting with express router 

```js  
```

# 9 more 

```
1. Authentication and Authorization
Learn about implementing authentication mechanisms (e.g., JWT, OAuth) to secure your routes and resources.
Understand authorization strategies to control access based on user roles and permissions.
2. Validation and Error Handling
Incorporate validation libraries (e.g., Joi, Express Validator) to validate user inputs and ensure data integrity.
Improve error handling techniques to provide meaningful error messages and handle different types of errors more effectively.
3. Database Relationships
Explore more complex database relationships such as one-to-many, many-to-many, and embedded documents to understand how to structure data efficiently.
4. Advanced Middleware Usage
Dive deeper into middleware functions, including creating custom middleware for specific purposes like logging, request/response manipulation, or error handling.
5. RESTful API Design Principles
Learn about RESTful API best practices to design cleaner, more scalable, and maintainable APIs.
6. Testing
Familiarize yourself with testing frameworks (e.g., Jest, Mocha) and learn to write unit tests and integration tests for your Express routes and MongoDB models.
7. Performance Optimization
Explore techniques to optimize performance, such as caching strategies (e.g., Redis) and database indexing.
8. Async/Await and Promises
Gain a deeper understanding of asynchronous JavaScript, including async/await syntax and handling promises effectively in Express routes.
9. Deployment and Scalability
Learn about deploying Express applications to different platforms (e.g., Heroku, AWS, Azure) and scaling strategies to handle increased traffic.
By delving into these areas, you'll expand your knowledge and be better equipped to build robust and secure web applications using Express and MongoDB. Keep practicing and applying these concepts in your projects to reinforce your understanding.
```
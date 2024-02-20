# Express

- ## Set up Express

```js
const express = require("express");
const app = express();
const port = 3000;

// Middleware code

app.listen(port, () => {
  console.log(
    "Express is the option to go\nThe server has started on port",
    port
  );
});
```

- ## Set Routs

```js
app.get("/", (req, res) => {
  res.send("Hello, world!");
});
```

- ## Dynamic Routs

```js
app.get("/tshirt/:id", (req, res) => {
  const ID = req.params.id; // Here, `id` is a dynamic route parameter
  // Process the ID or perform actions based on the dynamic route
});
```

- ## Send file

```js
// `root` is the directory where the file exists
app.get("/html", (req, res) => {
  res.sendFile("index.html", { root: __dirname });
});
```

- ## Redirect

```js
app.get("/oldRoot", (req, res) => {
  res.redirect("/newRoot");
});
```

- ## Middleware

```js
app.use(function (req, res, next) {
  console.log("Middleware called");
  next();
});
```

- ## 404

```js
// This middleware should be placed at the end to handle 404 errors
app.use((req, res) => {
  res.status(404).send("<h1>404 Page not found</h1>");
});
```

- ## Types of requests

```
Read    --> GET
Create  --> POST
Update  --> PUT
Delete  --> DELETE
```

# 6 Folder Structure

```
controllers {
  // CRUD operation functions (create, get, update, delete)
}

middlewares {
  // Custom middleware functions
}

models {
  userSchema // Database schema definitions
}

routes {
  // Routes that connect to CRUD operation functions
}

setup {
  setupMongoDB // MongoDB setup code
}

```

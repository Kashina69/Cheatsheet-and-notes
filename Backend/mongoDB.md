# MongoDB

- ## Set up Mongoose

```js
// You have to do this in the setup dir name as dbConnection.js
const mongoose = require("mongoose");

const connectDB = async () => {
  try {
    const connect = await mongoose.connect("mongodb+srv://DBname:password@cluster0.pnmvgo1.mongodb.net/");
    console.log("Database Connected:", connect.connection.host);
  } catch (err) {
    console.error(err);
  }
};

module.exports = connectDB;

```

- ## import database in main file

```js
// do this in index.js
const connectDB = require("./setup/dbConnection.js");
connectDB();
```

- ## Create Schema

```js
// models/userSchema.js
const mongoose = require("mongoose");

const userSchema = mongoose.Schema({
  name: {
    type: String,
    required: true,
  },
  email: {
    type: String,
    required: true,
  },
  password: {
    type: String,
    required: true,
  },
});

module.exports = mongoose.model("ModelName", userSchema);

```

- ## Setup CRUD routes

```js
const router = require("express").Router();
const {
  createUser,
  getUser,
  updateUser,
  deleteUser,
} = require("../controllers/CRUD");

router.route("/getUser").get(getUser);
router.route("/createUser").post(createUser);
router.route("/updateUser").put(updateUser);
router.route("/deleteUser").delete(deleteUser);

module.exports = router;

```

- ## Create User
  All of this will happen in the controllers/CRUD.js

```js
const User = require("../models/userSchema");

const createUser = async (req, res) => {
  try {
    const user = await User.create({
      name: req.body.name,
      email: req.body.email,
      password: req.body.password,
    });
    res.status(201).json({ user });
  } catch (err) {
    res.status(500).json({ error: err.message });
  }
};

module.exports = { createUser, getUser, updateUser, deleteUser };

```

- ## Get user

```js
const User = require("../models/userSchema");

const getUser = async (req, res) => {
  try {
    const users = await User.find();
    res.status(200).json({ data: users });
  } catch (err) {
    res.status(500).json({ error: err.message });
  }
};

module.exports = { createUser, getUser, updateUser, deleteUser };

```

- ## Update Users

```js
const User = require("../models/userSchema");

const updateUser = async (req, res) => {
  try {
    const user = await User.findByIdAndUpdate(req.params.id, req.body, {
      new: true,
    });
    res.status(200).json({ user });
  } catch (err) {
    res.status(500).json({ error: err.message });
  }
};

module.exports = { createUser, getUser, updateUser, deleteUser };

```

- ## Delete Users

```js
const User = require("../models/userSchema");

const deleteUser = async (req, res) => {
  try {
    const user = await User.findByIdAndDelete(req.params.id);
    res.status(200).json({ user });
  } catch (err) {
    res.status(500).json({ error: err.message });
  }
};

module.exports = { createUser, getUser, updateUser, deleteUser };

```

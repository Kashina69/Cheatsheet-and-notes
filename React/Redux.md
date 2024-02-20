# Redux

- ## App.js

```JSX
import { Provider } from "react-redux";

// when we are importing store from store.js we wont write Store caus this is not a component but its just a value
import store from "./store/store";

function App (){
    return(
        <>
            <Provider store = {store}>
                <RouterProvider router={router}/>
            </Provider>
        </>
    )
}
```

- ## Store/store.js

```JSX
import { configureStore } from "#reduxjs/toolkit";
import rootReducer from"./reducer";

const store = configureStore({
    reducer:rootReducer,
    });

export default store
```

- ## Store/reducer.js

```JSX
import { createAction, createReducer } from "@reduxjs/toolkit";
const incrementByAmount = createAction("counter/incrementByAmout");
const initialState = { value: 0};
const rootReducer = createReducer(initialState, (builder)=>{
    builder.addCase(incrementByAmount, (state, action) =>{
        state.value += action.payload;
    });
})
export {incrementByAmount}
export default rootReducer;
```

- ## Update the value

```JSX
import store from "../store/store";
import { incremnetByAmount } from "../store/reducer";
function Contact(){
    return( <button onClick = {()=>store.dispatch(incrementByAmount(5))}>increment by 5</button>
)}
```

- ## Get the state

```JSX
    import {useSelector} from "react-redux"
    function Register(){
        // This line to get the state in any file
        const valueOfTheState = useSelector((state)=> state.value);
        return( <h1>{valueOfTheState}</h1>) }
```

- ## Go to new rout without reloading and resetting the state

```JSX
    import {Link} from "react-router-dom";
    <Link to="/Rout">Link to the Rout</Link>
```

# Redux with Local Storage

- ## Install redux-persist

```JSX
    npm install redux-persist
```

- ## Store/store.js

```JSX
    import { configureStore } from "#reduxjs/toolkit";
    import { persistReducer, persistStore } from "redux-persist";
    import storage from "redux-persist/lib/storage";
    import rootReducer from"./reducer";

    const persistConfig ={
        key:"root",
        storage,
    }
    const persistedReducer = persistReducer(persistConfig, rootReducer);
        let  store = configureStore({
            reducer: persistedReducer,
        });

    export { store, persistor };


    // And when we will import store in any file we have to do
    import {store} from ../Store/store
```

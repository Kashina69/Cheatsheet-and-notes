## No reload on submit button click

```javascript
function handleRegister(event) {
  event.preventDefault();
  console.log("Hello world");
}

<button onClick={handleRegister}>Submit</button>;
```

# import Images 
- ## for the public dir
```jsx 
import Pic from './images/pic.png'
// this because the public is supposed to serve assets
```
- ## from the src/assets dir  
```jsx
import pic from '../images/pic.png'
// in this case we are going one step above the components dir and then landing to the src dir then moving to images dir 
```


#  props from child to parent 
- ## child code 
```jsx
    export const child = (props)=>{
        const handleClick = () =>{
            let dt = "Data from the child"
            props.getData(dt)
        }
    }
```

- ## parent code
```jsx 
function App(){
    const getData=(data)=>{
        console.log(data);
    }
    return{
        <child myClick = {getData}>
    }
}
```

# import from env file in react
- ## Make a ENV file (.env.local)
```env
BASE_API_URL ="https://mysite.com"
API_KEY = "hello1234"
```
- ## In the react file 
```jsx
<h1>{import.meta.env.BASE_API_URL}</h1>
<h1>{import.meta.env.API_KEY}</h1>
```

- ## If using vite 
```Env 
VITE_BASE_API_URL ="https://mysite.com"
VITE_API_KEY = "hello1234"
```
```jsx 
<h1>{import.meta.env.VITE_BASE_API_URL}</h1>
<h1>{import.meta.env.VITE_API_KEY}</h1>
```

# Conditional rendering in react

```jsx
{isTrue && {"Print this"}}

{ifTrue? {"Do this"} : {"Other Wise do this"}}
```
# Map 

```jsx
const items = ['Item', 'Item1', 'Item2', 'Item3'] ;

items.map((item, index)=>(
    <li key={i}>{i} --- {item}</li>
))
```

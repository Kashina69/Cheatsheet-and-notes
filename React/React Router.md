#  React router dom

- ## App.js

```JSX

import {createBrowserRouter , RouterProvider} from "react-routerdom"
// To make routs and then in elementToPass tell which screen you want to show like home about etc
    const router = createBrowserRouter([
        {
            path:"/",
            elementToPass: <Home/>
        },
        {
             path:"about",
            elementToPass: <About/>
        }
    ])

// To Implement RouterProvider

    function App(){
        return(
            <div>
                <RouterProvider router={router}/>
            </div>
        )
}
```

- ## Link

```JSX
// FOR GOING TO ANY ROUT MADE BY REACT-ROUTER
    import {Link} from "react-router-dom"
    <Link to = "/RoutName" />
```

- ## Navigate

```JSX
import {Navigate} from "react-router-dom"
<Navigate to ="/Dashboard" replace={true}>
```

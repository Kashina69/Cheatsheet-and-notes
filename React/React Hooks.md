# useState

```JSX
const [email, setEmail] = useState('');

<input type="text" value={email} onChange={(e) => setEmail(e.target.value)} />

// Email value is: {email}

```

# useEffect

The dependency array in useEffect is empty ([]), indicating it runs only once on component mount. You should add dependencies within the array if you want the effect to re-run when certain values change.

```JSX
   useEffect(() => {
  // Specify the effect logic here
}, []);

```

# useMemo

```JSX
const expensiveResult = useMemo(() => {
  return doSomeExpensiveCalculation(count);
}, [count]);

// This will recompute 'expensiveResult' only when 'count' changes
```

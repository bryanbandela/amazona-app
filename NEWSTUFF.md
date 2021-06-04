I. Deconstructing props (it could be an object or array depending on what it is)
const {} = props

II. Route & BrowserRoute aka Router
npm i react-router-dom

1. import {Route, BrowserRoute as Router, Link} from "react-router-dom"

<Router>
<nav>
<ul>
<li>
<Link to="/">Home</Link>
</li>
<li>
<Link to="/About">About</Link> Using link will do client-side routing unlike anchor tag which reloads everything
</li>
</ul>

</nav>
//Route needs two parameters: path & component
//You can add here any code that you want
<Route path="/" exact component={Home}> 
<Route path="/about" component={About}>//if you don't add "exact here you will get both the Home & about content when you render About

//What this code does is when the user goes to the "/" it will go to the "Home" component (Make sure you import Home & About in your file)
</Router>

III. params
Make sure you convert the id from the params to number
const product = data.products.find(
(x) => x.\_id === Number(props.match.params.id)
)

IV. To trigger the autocomplete (aka IntelliSense)

1. Ctrl + space

V. Node server

1. You can add ("type": "module") after "name" in the json package so you can use the import/export feature in node.

VI. Nodemon

1. npm i --save-dev nodemon (for dev mode)

2. inside json package, inside the object "scripts"
   "start": "nodemon --watch backend --exec node --experimental-modules backend/server.js"

VII. Axios

To load products from backend : Inside the frontend folder, Add in the json package under name
"proxy":"http://127.0.0.1:5000"

Axios is a library to send to send Ajax request to server.
In frontend folder, run npm i axios.

In homeScreen:
export default function HomeScreen() {
const [products, setProducts] = useState([]);
useEffect(() => {
const fetchData = async () => {
const { data } = await axios.get('/api/products');
setProducts(data);
};
fetchData();
}, []);

return (

<div className="row center">
{products.map((product) => (
<Product key={product._id} product={product} />
))}
</div>
);
}

VIII. ESLINT
To write cleaner codes

IX. Redux
To manage the state of our app
we create a file store.js inside frontend
we define an initial state & reducer (reducer is function that takes 2 params which returns the data from data.js)
we then define a store which takes 2 params (initialState & reducer) using the createStore function from redux and we export store

In the index.js we wrap the <App> with <Provider store={store}><App/></Provider> importing {Provider} from react-redux

download the redux dev tools in chrome

In frontend: npm i redux-thunk to make it possible to send Ajax request in our redux action
const store = createStore(reducer, initialState, compose(applyMiddleware()));

In HomeScreen, we'll fetch data from backend. Instead of having Ajax request in components, we're gonna move it into action.
To create an action we must create some constants for that action.

- src/constants/productConstants.js
- Define 3 [product] constants in that folder constants (the async nature of the ajax request requires 3 constants)
- Then define [product] actions to get list of products in a new folder inside src called "actions" : src/actions/productActions.js

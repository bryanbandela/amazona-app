I. Tools

1. VS Code + VS Code Extension
2. MongoDB (Community: free version)
3. Postman : to test API
4. NodeJS
5. Browser

II. Website Template

1. Create Amazona folder
2. Create template folder
3. HTML : Add header, main & footer
4. CSS : Styles elements

III. Display products

1. Create a div for products: inside this div all the product will be there

IV. Create a React App

1. Run "npx create-react-app frontend" inside the directory of project
2. npm start (cd to frontend folder)
3. Remove unused files
4. Copy index.html content to App.js (Make sure you remove any sorts of comments)
5. Copy style.css content to index.css
6. Replace class with ClassName

V. Create rating & Product component

1. create components/Rating.js
2. create div.rating
3. style div.rating, span and last span
4. Create Product component
5. Use rating components

VI. Build Product Screen

1. Install react-router-dom (cd to frontend & npm install react-router-dom)
2. Use BrowserRouter & Route for Home Screen
3. Create HomeScreen.js
4. Add product list codes there
5. Create ProductScreen.js
6. Add new Route from product details to App.js
7. Create 3 columns for product image, info and action

VII. Create NodeJs Server

1. run npm init in root folder
2. Update package.json set type: module
3. Add .js to imports
4. npm install express
5. create server.js
6. add start command as node backend/server.js
7. require express
8. create route for / return backend is ready.
9. move products.js from frontend to backend
10. create route for /api/products
11. return products
12. run npm start

VIII. Load Products From Backend
Inside the frontend folder, Add in the json package under name
"proxy":"http://127.0.0.1:5000"

1. edit HomeScreen.js
2. define products, loading and error.
3. create useEffect
4. define async fetchData and call it
5. install axios
6. get data from /api/products
7. show them in the list
8. create Loading Component
9. create Message Box Component
10. use them in HomeScreen

Axios is a library to send to send Ajax request to server.
In frontend folder, run npm i axios. Axiois is one of the ways to send http request (remember Angela Yu's course)

useEffect()

IX. Install ESlint For Code Linting

1. install VSCode eslint extension
2. npm install -D eslint from root project (-D : is for development only, not production)
3. run: ./node_modules/.bin/eslint --init
4. Create ./frontend/.env
5. In the .env file Add SKIP_PREFLIGHT_CHECK=true (since we'll be using eslint in root folder we need to disable preflight-check in the frontend folder)
6. cd frontend & npm start (Make sure Node is also running)

X. Add Redux to Home Screen
We'll use redux to get products from backend. It also controls the state of our app

1. npm install redux react-redux (cd frontend)
2. Create store.js in frontend to create a redux store(initial estate & reducer)
3. initState= {products:[]}
4. reducer = (state, action) => switch LOAD_PRODUCTS: {products: action.payload}
5. export default createStore(reducer, initState)
6. Edit HomeScreen.js
7. shopName = useSelector(state=>state.products)
8. const dispatch = useDispatch()
9. useEffect(()=>dispatch({type: LOAD_PRODUCTS, payload: data})
10. Add store to index.js

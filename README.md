# coffee-palace-ui
React App For our Coffee Palace, calls the **coffee-palace** Backend Application.

JSX  : The HTML, CSS and JS code rendered by the using a declarative syntax in the object.

Q : What is React?

A : 
  - Extremely Popular Declarative, Component Based, State-Driven, JS Library, created by Facebook and is extremely popular.
  - React reacs to the changes in the states by re-rendering the state objects.
  - React is a library rather than a framework. Some examples of Frameworks build on top of react are : Next.JS and Remix.

Q : Why not use Vanilla Javascript?

A : 
  - Server side rendering was complicated. Then JQwery came and rise of single page client side rendering (Single Page App or SPA) took place.
  - This was then moved towards the Web Development at the client side.
  - There are several problems with using client side single page app using Vanilla JS.
  - Requires a lot of direct DOM manipulation and Traversing - Spagetti Code
  - Data is usually stored in DOM, shared across the entire app
  -  HTML was the owner and JS was used inside a script tag. That is now reversed.

    
Q : Why do FE framework exists?

A : 
   - Keeping a UI in sync with Data is really hard and a lot of work.
   - Correct way of structuring and writing code
   - Consistent way of building FE Applications

Q : States vs Props.

A : 
  - States are command state variables inside the class.
  - Props are the parameters passed to other JSX Objects.

______


**Setting Up the Development Environment**

- Look for the URL "react.new" on web to redirect to the sandbox : codesandbox.io
- For local setup, Install Node JS LTS version. Not sure if already using? Use commands "node -v" and "npm -v" in the terminal.

**2 Ways of Creating the App :**
1. Create React App : Jest, Prettier, ESLint inbuilt. Webpack inbuilt (old technology and Slow). Best for Tutorials. 
2. VITE : Fast refresh, fast budling, but needs setting up tools manually, like ESLint, Prettier, and Test Frameworks. Best for Prod Ready Applications.


Tip : React suggests using Next.js for server side development as it supports Routing, Data fetching, Server side rendering. But vanilla react applications are great too and all of the developers not necessarily need all the tech in Next.js. Also for learning, get started with Vanilla React App, and then go for Next.js.

**The very first react app code, as basic entity :** 

    <!DOCTYPE html>
    <html lang="en">
      <head>
      <meta charset="UTF-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <title>First</title>
    </head>

    <body>
      <div id="root"></div>
      <script
        src="https://unpkg.com/react@18/umd/react.development.js"
        crossorigin
      ></script>
      <script
        src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"
        crossorigin
      ></script>
      <script>
        function App() {
          const [timeState, setTimeState] = React.useState(
            new Date().toLocaleTimeString()
          );
          const time = new Date().toLocaleTimeString();
          React.useEffect(function () {
            setInterval(function () {
              setTimeState(new Date().toLocaleTimeString());
            }, 1000);
          });
          return React.createElement(
            "header",
            (mytime = `${time}`),
            `Test Message at ${timeState}`
          );
        }
        const root = ReactDOM.createRoot(document.getElementById("root"));
        root.render(React.createElement(App));
      </script>
    </body>
    </html>

**Creating the first App :** 

1. `npm create-react-app <NAME_OF_YOUR_FIRST_APP>` and click `Y`.
2. Run the App once completed using `npm start`.



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



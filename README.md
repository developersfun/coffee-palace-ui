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

**USING SOME OF THE Language Related Methods :**

*For the data given below: 

`const data = [
  {
    id: 1,
    title: "The Lord of the Rings",
    publicationDate: "1954-07-29",
    author: "J. R. R. Tolkien",
    genres: [
      "fantasy",
      "high-fantasy",
      "adventure",
      "fiction",
      "novels",
      "literature",
    ],
    hasMovieAdaptation: true,
    pages: 1216,
    translations: {
      spanish: "El señor de los anillos",
      chinese: "魔戒",
      french: "Le Seigneur des anneaux",
    },
    reviews: {
      goodreads: {
        rating: 4.52,
        ratingsCount: 630994,
        reviewsCount: 13417,
      },
      librarything: {
        rating: 4.53,
        ratingsCount: 47166,
        reviewsCount: 452,
      },
    },
  },
  {
    id: 2,
    title: "The Cyberiad",
    publicationDate: "1965-01-01",
    author: "Stanislaw Lem",
    genres: [
      "science fiction",
      "humor",
      "speculative fiction",
      "short stories",
      "fantasy",
    ],
    hasMovieAdaptation: false,
    pages: 295,
    translations: {},
    reviews: {
      goodreads: {
        rating: 4.16,
        ratingsCount: 11663,
        reviewsCount: 812,
      },
      librarything: {
        rating: 4.13,
        ratingsCount: 2434,
        reviewsCount: 0,
      },
    },
  },
  {
    id: 3,
    title: "Dune",
    publicationDate: "1965-01-01",
    author: "Frank Herbert",
    genres: ["science fiction", "novel", "adventure"],
    hasMovieAdaptation: true,
    pages: 658,
    translations: {
      spanish: "",
    },
    reviews: {
      goodreads: {
        rating: 4.25,
        ratingsCount: 1142893,
        reviewsCount: 49701,
      },
    },
  },
  {
    id: 4,
    title: "Harry Potter and the Philosopher's Stone",
    publicationDate: "1997-06-26",
    author: "J. K. Rowling",
    genres: ["fantasy", "adventure"],
    hasMovieAdaptation: true,
    pages: 223,
    translations: {
      spanish: "Harry Potter y la piedra filosofal",
      korean: "해리 포터와 마법사의 돌",
      bengali: "হ্যারি পটার এন্ড দ্য ফিলোসফার্স স্টোন",
      portuguese: "Harry Potter e a Pedra Filosofal",
    },
    reviews: {
      goodreads: {
        rating: 4.47,
        ratingsCount: 8910059,
        reviewsCount: 140625,
      },
      librarything: {
        rating: 4.29,
        ratingsCount: 120941,
        reviewsCount: 1960,
      },
    },
  },
  {
    id: 5,
    title: "A Game of Thrones",
    publicationDate: "1996-08-01",
    author: "George R. R. Martin",
    genres: ["fantasy", "high-fantasy", "novel", "fantasy fiction"],
    hasMovieAdaptation: true,
    pages: 835,
    translations: {
      korean: "왕좌의 게임",
      polish: "Gra o tron",
      portuguese: "A Guerra dos Tronos",
      spanish: "Juego de tronos",
    },
    reviews: {
      goodreads: {
        rating: 4.44,
        ratingsCount: 2295233,
        reviewsCount: 59058,
      },
      librarything: {
        rating: 4.36,
        ratingsCount: 38358,
        reviewsCount: 1095,
      },
    },
  },
];`

*Below are the basic Language Operations : 
`// Data Getter
function getBooks() {
  return data;
}

// Data Object Getter with ID
function getBook(id) {
  return data.find((d) => d.id === id);
}

const books = getBooks();

//Extracting fields out of an object
const { title, author, genres, pages, publicationDate } = getBook(2);

// Rest Operator(...), Creates a list of remaining objects in genre
const [prim, secon, ...others] = genres; //... is rest operator. Also used as spread operator.

console.log(secon);
console.log(others);
console.log(title, author);
console.log(getBook(2).author);

//Spread Operator example, adds the additional elements in the new array arr.
const arr = [...genres, "Comedy", "RomCom"];

const book = getBook(1);

//Object cloning using spread operator, also helps in updating or adding more fields
const updatedBook = {
  ...book,
  moviePublicatioDate: "2021-12-19",
  pages: "1000",
};

//Template Literals
const summary = `${title} is a ${pages} pages long book written by ${author} in the year ${
  publicationDate.split("-")[0]
}`;
console.log(summary);

//Ternary Operator
console.log(pages > 1000 ? "long book" : "short book");

//Falsy Values : false, '', 0, null, undefined

//Short circuiting occurs when we have :
// 1. First Argument as Falsy value in AND operator, and if false, it returns false, otherwise returns second argument. Eg,
console.log(false && "My Name"); // short circuits and returns false
console.log(true && "My Name"); // returns My Name
// 2. First Argument as Truthsy value in OR operator
console.log(0 || "My Name"); // returns My Name
console.log(true || "My Name"); // short circuits and returns true

// Example of where to find short-circuiting useful
const translation = book.translations.spanish;
console.log(translation && "Not Translated");

//Another type of Short Circuiting using collease operator
const count = book.reviews.librarything.reviewsCount ?? "No Reviews";

function getTotalReviews(book) {
  //Optional Chaining :
  // const goodReads = book.goodReads?.reviewsCount;
  // const lib = book.librarything?.reviewsCount;

  //Short Circuiting using coallese operator along with Optional Chaining
  const goodReads = book.goodReads?.reviewsCount ?? 0;
  const lib = book.librarything?.reviewsCount ?? 0;
  return goodReads + lib; //returns 0 instead of NaN when using collease operator
}

console.log(getTotalReviews(getBook(2)));`


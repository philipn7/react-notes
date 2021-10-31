# Introduction
## What is react?
Client-side JavaScript library used to create modern, reactive user interfaces for the web. Declarative, component focused.

- React can be used to control Single Page Applications (SPA) or control parts of a page (widget)
- React doesn't run in the browser directly. It is compiles into JS which the browser understands.

## React Component
Like a regular JS function but returns JSX. The component can be passed to the index.js file which will append the component using ReactDOM.render().

## JSX Example
```
    <div>
      <h1>My Todos</h1>
      <div className="card">
        <h2>TITLE</h2>
        <div className="actions">
          <button className="btn">Delete</button>
        </div>
      </div>
    </div>
```
NOTE: html uses 'class' as the keyword but JSX uses 'className'

## How do you pass arguments into a react component?
- Have `props` as an argument into the component. Attributes defined in JSX are now key-value pairs in props.
```
function Todo(props) {
  return (
    <div className="card">
      <h2>{props.text}</h2>
      <div className="actions">
        <button className="btn">Delete</button>
      </div>
    </div>
  );
}
```
Use `{}` to convert plain text into JS.

## JavaScript vs React approach
In JS, we add an event on a button using a imperative approach (We describe what should happen): 
`document.querySelector('button').addEventListener('click')` 

Whereas, react is declarative, we describe what we want. 
`<button className="btn" onClick={someHandler}>`

## State
Register different states and allows us to do things based on those states.
`useState()` always returns two elements. First element is the current state. The second is a setter function.

## Routing
Route 'page' components in a single page website.
In index.js...
```
import { BrowserRouter } from 'react-router-dom';

ReactDOM.render(
  <BrowserRouter>
    <App />
  </BrowserRouter>,
  document.getElementById('root')
);
```
<App/> is wrapped with the BrowserRouter component.

In the main App.js...
```
	  <Route path='/favourites'>
        <FavouritesPage />
      </Route>
```
By default, Route will match all paths. Wrap the routes in the `Switch` react component to only allow one page to be routed.
By default, Switch will stop once it finds a partial match. To only have exact matches, use the `exact` tag inside the route component.

Use the `Link` component to create links to react routes. 'aref' relies on communication to the server while the Link component doesn't.

## CSS Styling Modules
End the filename with '.module.css'. Then import the css file:
`import something from './thing.module.css'`
Use this to scope the css file to that component.

## Outputting lists of data
```
function AllMeetupsPage() {
  return (
    <section>
      <h1>All Meetups</h1>
      <ul>
        {DUMMY_DATA.map((meetup) => {
          return <li key={meetup.id}>{meetup.title}</li>;
        })}
      </ul>
    </section>
  );
}
```
Use the map() function to return a list. NOTE: Needs a unique identifier defined with `key=`

## Wrapping Classes
Components can be wrapped around other JSX code. For example, a `<Card></Card>` component can wrap card styling.
Inside the Card component, the `props.children` argument can be used to pass whatever is between `<Card></Card>`.

```
function Card(props) {
  return <div className={classes.card}>{props.children}</div>;
}
```
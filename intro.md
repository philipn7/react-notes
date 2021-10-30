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
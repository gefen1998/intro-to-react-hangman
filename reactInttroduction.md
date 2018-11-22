# React is - quite simply - a JS library for building User Interfaces. It is a great tool for building *SPAs* (Single Page Applications).Facebook has created React and open-sourced it for our use. =>

*In short, an SPA just means that the app re-writes the current page with new data whenever a change is made, as opposed to always asking the sever for a new page (new HTML).

# So far, any time we wanted to display/update information on our webpage (i.e. building our UI), we’ve used jQuery.
there’s nothing really wrong with jQuery, However it can become a mess to manage when your project grows.
<!-- https://reactjs.org/ -->

React is an extremely popular framework that is used throughout the industry. one of the most touted benefits is React’s speed.
#When we worked with jQuery and proper data flow, we always re-rendered our entire page’s data. We may not notice any performance issues on small-scale apps, but once our apps become bigger, then re-rendering everything isn’t as feasible.
Even just conceptually it makes sense to only update the thing that changed, rather than change everything.

# React comes with what’s known as a Virtual DOM - they did not invent this concept (and we’ll go more in depth later) - but briefly: the Virtual DOM is a copy of our actual DOM that is purely a *normal JS object.*

<!-- What is the Virtual DOM? -->
The virtual DOM (VDOM) is a programming concept where an ideal, or “virtual”, representation of a UI is kept in memory and synced with the “real” DOM by a library such as ReactDOM. This process is called reconciliation.

This approach enables the declarative API of React: You tell React what state you want the UI to be in, and it makes sure the DOM matches that state. This abstracts out the attribute manipulation, event handling, and manual DOM updating that you would otherwise have to use to build your app.

# Using the Virtual DOM, React does the following:
* Once an event happens, figure out what needs to change in the Virtual DOM
* Update the Virtual DOM accordingly (if it needs to update)
* Compare the Virtual and Real DOM
* In the comparison, React will look for differences
* When it finds a difference, it will update the actual DOM in that one location
# This may seem like a lot, but ultimately it is much easier and faster to work with objects than to render the DOM. So even though React does some behind-the-scenes work before updating the DOM, it eventually only has to update the relevant element(s) in the DOM.
* for exe - one div is physically affected when we delete an element.
* React is faster: Rendering the DOM is expensive, whereas manipulating objects is (generally) much cheaper. React renders less and manipulates objects more using the Virtual DOM.

<!-- START REACTING -->
<!-- Setup -->
To start a new react project we will use npm to do a lot of the heavy lifting for us. To that end, we’re going to install an npm package called create-react-app globally (will allow us to create a react application with all the necessary setup.)
Notice the global -g install so that we can use this command from anywhere.
# npm install -g create-react-app

The next part is to use that package, with a name for the project we want to create.
# create-react-app hangman

<!-- File Structure -->
Open up the project using
# code hangman
We already know node_modules, public, .gitignore, package.json, and the README.md.
So really all that’s new is the src folder and its contents. Of those, we’re really only interested (for now) in # App.js and index.js #

# npm start
* If you check out package.json you’ll see that under scripts.start we have react-scripts start - this is what we’re executing when we do npm start - this is what actually starts our react application

# index.js - It is a normal JavaScript file, You will likely never change it
ReactDOM.render(<App />, document.getElementById('root')); registerServiceWorker();
* ReactDOM gives us high-level methods for operations related to the DOM. 
*  One such method is…
ReactDOM.render(...) - this takes two parameters:
# What to render
# Where to render it …and renders the first param

<App /> - this is what we’re going to render.
# Though it looks remarkably similar, it’s not HTML. It is JSX (a syntax extension to JS which will eventually be used to render HTML). it is representing a component

document.getElementById('root') - this is where we’re going to render. find something on the DOM with an id of ‘root’

# ignore the registerServiceWorker() line 
# where is this root to which we’re adding whatever is? That’s in your index.html file - a file you will, again, not really want to touch.
* Inside the file, between all the comments, you should see a simple div. This is where everything in our app will render, eventually:
<div id="root"></div>

* ReactDOM.render(…) : take some JSX*, put it in the element with ID root.
* Behind the scenes, React takes this JSX and uses it to generate HTML. 
# JSX is not HTML - it is closer to JS.

* dd a class attribute to the h1 above, we would have to use className (camelCase) instead, like this:

ReactDOM.render(
    <h1 className='goldClass'> Hai. </h1>, 
    document.getElementById('root')
);

* This will be true for event handlers as well ( onClick instead of onclick )




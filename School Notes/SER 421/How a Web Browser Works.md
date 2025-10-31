# Topic: How  Web Browser Work
## How Web Browser Work
### Browser Main Components and Flow
1. UI
2. Browser engine -  query/manipulate rendering engine
3. Rendering engine: rendering
	- Main Flow
		- Parsing HTML to construct the DOM tree
		- Render tree construction
		- Layout of the render tree
		- Painting the render tree
4. Networking
5. UI backend - OS interface for widgets
6. JS interpreter
7. Data Storage
### HTML Parsing Algorithm
- Cannot be parsed using regular top down or bottom up parsers
	- Traditional error tolerance
	- Browsers create custom parsers for parsing HTML
- Parsing algorithm consists of tokenization and tree construction
	- Tokenization is lexical analysis: Parsing input into tokens
		- Tokens include start/end tags, attribute names/values
	- Tokens are given to the tree constructor
### Javascript Execution
- Execute scripts synchronously: When script tag is reaches it halts HTML parsing
	- Attributes to modify this default
		- Defer: Document continues to parse
		- Asynchronous: Script is parsed and executed on a different thread
- Speculative parsing: Fetching external resources on other threads to not slow down main parsing
	- Does not specify the DOM at all, just optimizes the retrieval of external resources
- Javascript and CSS Parsing
	- CSS does not change the DOM
		- Doesn't halt HTML parsing
	- Javascript may ask for style information (CSS), so browsers have different strategies for blocking scripts if they access style information
### Render Tree Construction
- Tree of visual elements and the order they display
	- Enables painting contents in the correct order
		- encapsulated and specialized by type
- Render Tree and the DOM tree
### Render Style Computation
- Style is a very large construct, cause memory problems
- Finding matching rules for each element can cause performance issues
- Involves complex cascade rules that define the hierarchy of the rules
### Layout
- Flow layout: Displays everything from the tree and wraps around again
	- Causes a lot of jumping around
	- Seen a lot for banner ads
## Single Page Applications
### Recall: SPAs
- Server delivers an app to the browser not content
- Application runs in the browser and navigates the web resources it needs
- Advantages
	- Responsivity / UX interaction
	- More power to developers
	- Server side scalability and maintenance
	- Support for richer set of modern devices
- Disadvantage
	- Security
	- Browser incompatibility
	- Inconsistent rendering
	- Testing complexity
		- Classic fat client problem
### What Does This Desktop Model Look Like?
- Desktop widget collection of properties are a theme, Browser model properties are from CSS
- Browser uses Javascript to handle events and interact with the model
- Browser mostly uses CSS to decouple and optimize styling
## Javascript and the DOM
### The DOM
- DOM: WhatWG Living Standard
	- Standard for accessing parsed documents
	- Object model and programming interface for markup docs
### DOM Main Types Summary
- Document class
	- Represent top-level document
	- Properties
		- documentElement
			- Root element of the doc, HTML
	- Methods (HTML only)
		- getElementById
			- Returns element with specified id
		- getElementsByTagName
			- Returns HTML collection of elements with that tag name
- Node class
	- Represents node in DOM tree
	- Properties
		- attributes, childNodes, firstChild, lastChild, nextSibling, nodeName, nodeType, nodeValue, parentNode, previousSibling
	- Methods
		- hasAttributes, hasChildNodes, normalize, write
- Element class
	- Inherits Node methods plus has some extras
	- Methods
		- getAttribute, getElementsByTagName, hasAttribute
### Node vs Element
- Nodes: Nodes in the n-ary tree
- Element: Inherits from nodes
	- Correspond to the tags in an HTML doc
### HTML specific: HTMLElement
- innerHTML: Read/Write property giving HTML text inside element
## Javascript Event Handling
### Think of Desktop GUI Model
- App responds to events
	- Designate functions for certain events
	- Has listeners attached
### UI Event Handling
- General event handlers
	- onclick, ondblclick: User single or double click
	- onkeydown, onkeypress, onkeyup: User presses key when element has the focus
	- onmousedown, onmouseup: User presses mouse over element
	- onmouseover, onmouseout: Mouse moves over or leaves being over lement
	- onmousemove: Mouse moves while over element
- Specialized event handlers
	- input
		- onclick
		- onchange
		- onblur, onfocus
	- form
		- onsubmit, onreset
	- body
		- onblur
		- oneerror
		- onfocus
		- onload
		- onresize
		- onunload
	- img
		- onabort
		- onerror
		- onload
### Window Based Events and Handlers
- Events on the browser on the window object
	- Window is the global available to the JS code
	- Default scoped to the current tab
### DOM Events (When a Page Loads)
- Browser's parser executes each script as it encounters is
- Couple of problems
	- Script does something computationally expensive
		- Page will pause rendering
		- Creating an awkward UX for the end user
	- Script performs DOM manipulation as a side effect
		- Script will have a race condition between parser/renderer and the Javascript engine
		- Best practice is to put script at the end of the page
### Page Load Events
```js
<body onload="code" ...>
// Exectues code after the parser completes loading the page and all resources

<script src="URL-to-js" defer />
// Defer is a boolean attribute to ensure external script doesn't execute until page is parsed

<script src="URL-to-js" async />
// Async is like defer but loads parser to continue while a script is fetched, exectures when it's loaded

// Add an event listener to the DOMCOntentLoaded event
// Runs after parsing, but before rendering
```
## Javascript and Persistent Storage
### User Cases for Storage in a Browser
- Mobile device to work in disconnected mode
	- Involves the File API and/or AppCache
- Maintain conversational state
	- Long time problem for server and client side development
- Remember where a user is in the app
	- What your are used to doing on a desktop or mobile app
- Remember users and their preferences
	- Done with cookies
	- With combination of persistent storage on the server
### Javascript and Cookies
- Cookies originate on the server
	- Server requests to the client they be set in an HTTP response
	- Client accepts cookies and sends back on each request
- Document object has a cookie property
- Limitations
	- Storage size, multi-values as delimited strings, marshaling state in a string based format, potential privacy concerns, feel like a hack
### Deep Dive Into Browser Storage
```
session[local]Storage.setItem(key, value)
session[local]Storage.setItem(key)
session[local]Storage.removeItem(key)
session[local]Storage.clear()
```

- Session storage is only for how long user is on a website
- Local storage is stored in the server
### SQLite and IndexedDB
- Database provide scaling, querying, and understanding (ability to manage lots of data)
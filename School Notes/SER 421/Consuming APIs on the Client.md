# HTTP Review
## HTTP Review Lecture Video
- HTTP is the protocol of the web
	- Synchronous
	- Stateless
#### URLs
- Uniform Resource Locators
	- Address of an object or resource
	- Syntax is dependent on the scheme (protocol)
- Unsafe characters in a URL:
	- ;
	- ,
	- ?
	- :
	- @
	- =
	- &
#### Request Headers
- Accept: Indicates MIME types browser can handle
- Accept-Encoding: Indicates encodings the browser can handle
- Accept-Language: The human language preferred
- Authorization: User identification for password protected pages
- Connect: Persistent connection allowed the reuse of a socket
- Cookie: Gives cookies previously sent to client
- Host: Indicates host given in original URL
- DNT: Do Not Track, failed attempt to express client preferences on server side tracking of users
- If Modified Since: Client wants page only if it has been changed after specified date
- Referer: URL of referring web page, used by servers to log traffic
- User Agent: String identifying the browser making the request
#### Status Codes
- 2xx: Successful
- 3xx: Redirection
	- 301: Requested document permanently moved
	- 302: Found
- 4xx: Client error
	- 404: Resource not found
	- 400: Syntax error
	- 401: Unauthorized and 403 (forbidden)
	- 405: Method no allowed
- 5xx: Server error, valid request but couldn't fulfill
	- 500: Internal server error (Unhandled exception)
	- 501: Not implemented (Try again in the future)
	- 503: Service not available (Server process error)
#### Response Header
- Content type: Media type of content
- Content encoding: The way the document is encoded
- Content length: Number of bytes in the response
- Set cookie: Cookies the browser should remember
- WWW Authenticate: Authorization type and realm needed in Authorization header
# Managing State on the Web
## Types of State
- Application state: Lifecycle of your running processes
- User preferences state: State pertaining to a user that informs  their interactions with your apps
	- Cookies are usually the best for user preferences
	- Often server side
- User interface state: State of widgets
- Conversational state: Bounded interaction between we browser and web server
- Universal or World Model state: Central database local in the application
## Revisiting MVC
- Data plus behaviors that act independent
- Controller routes messages to the proper place in the model
- View is responsible for app specific input and output
- Model is the data our application interacts with
	- May be local data or world model state
- Controller and the model are often split between the client and the server
## Cookies
- Client side state solution
	- Server sends a simple name and value to client
	- Client returns same name and value when it connects to the same site
- Uses of cookies
	- Identifying a user ducint session
	- User preference state
	- Customizing a site (personalization)
### Different Types of Cookies
- Session cookie: Only used in memory in that session of the browser instance
- Persistent cookie: Lasts for specific time period
- Secure cookie: Only transmitted over HTTPS
- HTTPOnly: Prevents reading cookie values in javascript
### Cookies and Privacy
- Stores personal information that can be accessed by 3rd party websites
### Types of Cookies
- 1st party cookies: From the same domain
- 3rd party cookies: From another domain
# AJAX/Fetch
## AJAX
- Motivation: Replacing the page at a time model
	- Browser can send a post or get request
- Issues:
	- Non-interactive
	- Content driven
	- Server is doing all the work
- Ajax: Send data to be displayed as XML/JSON and render using JavaScript
### Basic AJAX Process
- JavaScript: Define object for sending HTTP Request
	- Initiate request
		- Get request object
		- Handle response
- HTML
	- Load AJAX enabled JavaScript
	- Designate control that initiates request
	- Give ids to input elements and empty placeholder elements
### Request Lifecycle
- 0 = unsent
- 1 = opened
- 2 = Header received
- 3 = loading
- 4 = Done
## Asynchronous Processing
- JavaScript uses an asynchronous, single threaded model
	- Single threaded nonblocking execution with 1 call stack and 1 heap 
- Callback is registered at the time the request for processing is made and that callback is put on a queue when processing completes
	- The event loop checks the queue of callback functions to see if there is an event handle
## Fetch
- Fetch gets URL and returns a Promise object
- Resolve response obj to JSON
- Chain handling that Promise to working with the actual JSON
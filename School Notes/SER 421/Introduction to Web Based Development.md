# Video Lecture
## Introduction to the Web
### How does the Web Work?
#### What happens?
1. Browser asks the Domain Name Service (DNS) to find the IP address of the server
2. Client opens a socket and sends an HTTP request (routed by the IP layer) to the server
3. Server listens on port 80, receives HTTP requests
4. Server process the request
5. Client receives the response and processes it for display to the user
#### HTTP: Network protocol
- Application layer protocol, typically built on TCP/IP
- Synchronous: Every request has one response
	- Stays up and waits for a request
- Stateless: Requests are independent of each other
#### Web Evolution
- Evolved from document/content delivery to an application delivery platform
- Originally network file sharing system
- Early websites focused on content delivery, and some still are
- High-bandwidth Internet access came about, the Web is now seen on the spectrum of content delivery to application delivery
#### Web X.0
- Web 1.0: Read only web (90s)
- Web 2.0: Read and write web
	- Birth of social media
- Web 3.0: Read, write, and execute
	- Semantic web
	- Machine readable/participatory
- Web 4.0: Read, write, execute plus concurrency
	- Intelligent interaction
	- Human/machine symbiosis
### Evolution of Web Software Application Architectures
#### Flexibility of Web
- How does the client (browser) work? What are its responsibilities?
	- How a browser processes a web response
	- Browser is a runtime environment
- To be a proficient web developer understand HTTP
- Responsibilities of the server
	- Server and clients in web apps have evolved overtime
		- Thin vs fat clients
	- Evolution comes a variety of server side platform and technology choices
#### Server side driven applications
-  Server driven applications: Thin client and fat server
	- Browser makes requests to retrieve content or process input
	- Server responds with HTML
	- Evolution of variety of architecture
		- CGIs (Common Gateway Interface): Process per request
		- Server side scripting (PHP): Mix of content and behavior
		- Component based (Servlets, ASP./NET): The first gen of behavior centric supporting platforms
			- Multithreaded and stateful
		- Functional (NodeJS): Single threaded, asynchronous, high-throughput
- Advantages
	- Less complex, more secure, more maintainable
	- Still useful for low bandwidth and low client computation
	- Page rendering does not do annoying "Page jumping around"
- Disadvantages
	- Poorer responsivity
	- Lacks sophisticated application functionality
	- Limits server scalability
#### Hybrid applications
- Server and client share responsibility for behaviors
- For more modern content management systems
- Banner ads a client calls to a server side network to give the ad
- Advantages
	- Improved responsivity/ UX interactivity
	- Personalization/Customization
	- Page rendering starts quickly
- Disadvantage
	- Poorly designed apps do not maintain a clean separation of concerns between the client and server
		- Inconsistency of what part is responsible for
	- Personalization/Customization
#### Single Page Application
- Application delivery not content delivery
- Application runs in the browser and navigates the web resources it needs
- Fat client is now fully responsible for the app
	- Server is responsible for shared state
- Advantage
	- Responsivity
	- Returns to clean SOC
		- App is only on the client not the server
	- Puts more power in the hands of app developers
	- Server side scalability and maintenance
- Disadvantage
	- Security
	- Browser incompatibility
	- Inconsistent rendering on client
	- Testing complexity
		- Fat client problem
#### Summary
- Content to application delivery
- fat server/ thin client to thin server/fat client
- Driving forces
	- Increased computing power
	- Priority on user interaction
	- Server side economics
## HTML5 and CSS

### HTML and HTML5
#### HTML 4.0
- Text with markup (<tag attr1="", attr2="">)
	- Tags enclosed in angle brackets (<*/H1> introduction<*/H1>)
- Important tags
	- html
	- head
	- body
	- Links (href)
	- form
- Examples of links to URL
```html
// Link to absolute URL
<A HREF=http://host/path/ch2.html>Chapter 2</A>
// Link to relative URL
<A HREF=./chapters/ch2.html>Chapter 2</A>
// Link to a section of a URL
<A HREF=ch1.html#Sec2>Sec. 2 of Chap. 1</A>
// Email
<A HREF=mailto: joe@author.org>Send the author email</A>
```
#### HTML Form
![[Pasted image 20250826195732.png]]
#### HTML5
- New semantic tags and microdata
- Updates to forms
- Now object types
	- Video, audio, canvas
- Includes CSS and JavaScript properties
- Updates to existing presentation tags
#### Semantic Tags
- Main: Denotes the main content of the page
- Section
- Article
- nav
- details: Additional details users can view or hide
- summary: Visible header for details
- mark: Defines marked or highlighted text
- time
- aside: Sidebar for style
- header
- footer
- figure and figcaption: Self contained content
#### Document Structure
- Document layout
	- Provides manipulation and appearance with JS and CSS
- Page Structure
	- Basic structure with head and body elements
- Block and Inline Structure
	- Block structure: Starts a new line
		- Used for DOM manipulation or CSS application a certain section
		- Span can also have the same function, no new line
	- Section and Article is also used similarly
#### Forms 2.0 in HTML5
![[Pasted image 20250826200536.png]]
- Types are indicated on a type attribute
	- Different types of inputs
	- Look up a specific input that can help
```html
<input type="XXX" ... >
```
#### Media Object Types
```html
<video>
<audio>
<canvas>: Creates a container area on the page that JS can then get reference to, and execute drawing commands
<svg>: Scalable Vector Graphics

```
### RWD and CSS
#### CSS in Brief
- Selector rules: (Declaratively) Identifying the CSS rule to apply to an element
	- Selectors may be grouped
	- Order they are declared
```css
tag { decl-1; decl-2;}
#id SAME /* select elements with id attr = id */
tag.class SAME /* select tag elements of a class */
```
- Media Queries: Logical true/false rules
	- 1st example grabs a specific stylesheet based on the rendering agent
	- 2nd example sets the background color if the screen is 720 pixels wide
```css
<link rel="stylesheet" href="my.css" media="screen">

@media screen and (width: 720px) { body { background-color: #00f; }}
```
- Box Model: Every HTML element has a box around it
![[Pasted image 20250826201921.png]]
#### Specifying CSS
- Specifying CSS options
```html
<link rel=“stylesheet” type=“text/css” href=“s.css”>
<style>…</style> /* specified in HEAD of HTML file */
<tag style=“p:v;…”>… /* inline style via attribute */
```
#### Rendering on the Web: The Problem
- Rise of mobile devices: New screen sizes
- Websites for desktop are unstable for mobile devices
- Solutions
	- Ignore it
	- Make a mobile website and a desktop website
	- Make adaptive website
	- Make a responsive website
#### Responsive Web Design
- Design and development should respond to user behavior and environment
- Provide optimal viewing experience
- Flexible grid based layout
- RWD relies heavily on Media queries, and module from CSS3 specs
- Pros
	- SOC - UI dev and back end devs
	- Focus on key factors
	- Long term money and time savings, easy maintenance
	- More consistent user experience
	- Better search engine optimization
	- Single URL
- Cons
	- focus on mobile or desktop?
	- Huge upfront cost for RWD research and design
	- Optimizing RWD site performance is not easy
	- Impact on performance
	- Potential incompatible issues with CSS media queries
#### Adaptive Design (A type of RWD)
- Design a set of fixed layouts
- Once loaded the structure doesn't change
- 6 standard resolutions: 320, 480, 760, 960, 1200, and 1600 px
- Problem: There are too many common screen sizes
#### Design Approaches
- Mobile first: Bottom up
	- Progressive enhancement
	- Develop with the lowest common denominator then progressively enhanced as the resolution increases
	- Pros
		- Focus on most vital parts
		- Focusing on delivering the best browsing experience
		- Explore new capabilities for mobile web
	- Cons
		- Demond higher learning curve
		- Slower to develop
- Desktop first: Top down
	- Graceful degradation
	- Use desktop resolution as starting point and gracefully degrades design
	- Pros
		- Faster development time
		- Designers and developers are more familiar with the process
	- Cons
		- Not mobile friendly
		- Tablet or mobile mode is a downgrade
		- Prone to accidental removal of vital features and content
## Interaction Design for the Web
### Basics of Interaction Design for the Web

### IxD Trends (Interaction Design)
- Interaction Design is subfield underneath User Experience  Design
	- Way users interact with UI
	- Data entry -> PC with mouse -> Web -> Mobile, Games, smart TVs, loT, AR/VR
- Devices drive nature of interaction and the types of events our UIs must handle
### Users, Goals, and Tasks = Flows
- Users
	- Who are they?
	- What are their work environments like?
	- How experienced are they with the technologies?
	- Mental models and vocab?
	- Personal characteristics?
	- Cultural differences?
	- Motivational differences?
- Goals: Main thing users are trying to achieve
- Tasks: How users do things to achieve their goals
### Workflow Patterns
- Hubs: Start a task and then comeback
	- Ideal for for situations that use multiple, discreet, single page forms
- Wizards: Step by step for multi page procedures that need to be in order
	- Ends with a verification after transferring data from step to step
- Guides: Like wizard but can revisit every step
	- Confirmation has to have a minimal amount of information
### Interaction Design Techniques
#### Progressive Disclosure
- Move complex and less frequently used options out of the main user interface and into secondary screens
	- Benefits
		- Prevents user from getting overwhelmed
		- Allows users to recognize what to do as they go along
		- Increases ease of use of the product and reduces chance for user error
	- Risks
		- Repeat user may not require progressive disclosure
		- Assumes the designer understands the most popular task for the user
#### Metaphors
- Product oriented conceptual model that map over to user oriented mental models
	- Icons that match the action
#### Modalities
- View mode: No changes to stored data
- Edit mode: Changes to stored data
- Also includes role based action controls to determine who can edit or only view
### In Context of UCD
- Process that validates user goals and tasks
- Storyboarding: Flow of the application
- Click stream analysis: Analyze interactions to see if it's being used the way it was planned
- Refinement
## Intro to Javascript and Typescript
### Intro to Javascript
- Language of the web
- NodeJS is a server side JS frameworks
- Topics
	- Variable, Operations, and Statements
	- Conditional and Loops
	- Arrays
	- Strings
	- Functions
	- Object basics and Prototypes
	- Static methods
### Intro to Typescript
- Address shortcomings of Javascript
	- Dynamically and weakly typed
	- Provides eval function
	- Prototype based language in terms of OO
	- Difficult to use at scale
	- Dynamic typing, eval loop, and confusing semantics leads to vulnerabilities
- Typescript is a superset of standard Javascript

# Flashcards
- https://wayground.com/join/game/U2FsdGVkX1%252B7U0AOnC8w48sVBmyUTFbP4YLp2e6DP2O4SLP3CZAUcF62mOazJfvcJRsySB0QBhqw%252FmjyRnxEgQ%253D%253D
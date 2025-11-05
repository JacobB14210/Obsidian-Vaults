# Web Frameworks
## Pros and Cons of Frameworks
- Pros
	- Reusable design leads to consistency
	- Understandable abstractions
	- Convenient features, simplify code
	- Has large active communities for support
	- Optimize performance
	- Good tools within modern web IDEs
- Cons
	- Obfuscating the low level API may cause difficulties in troubleshooting
	- Lose control from outsourced design
	- Frameworks changes all the time
	- Base APIs ensure you control compatibility
# The MVC (Model View Controller) Pattern
## Separation of Concerns
- Responsibilities of a system
	- Allows custom expertise and frameworks to be applied to each concern
	- Reinforces encapsulation, allowing for greater code maintainability
- Three important aspects
	- Data Access: How to access data in persistent storage
	- Business Logic: 100% independent of a specific application
	- Presentation: How information is presented to the client
## What is MVC
- Design pattern that supports SOC
	- Not specific to web applications
- Generic Steps
	- Client makes a request to a system or application
		- Action page oriented
		- Component event oriented
	- Incoming message is received by a controller
	- Delegated message handler processes the message
		- Invariant to web applications
		- Not dependent on message format
	- Handler produces a normalized response
	- Controller routes the message to the appropriate view to determine how to format the response for the client
		- HTML, JSON, XML
## Variations on MVC for GUIs
- Presentation Model: Represents the state and behavior of the presentation independently of the GUI controls used in the interface
- Front Controller Pattern: Web specific pattern that provides a point for all requests, then delegates those requests to the proper controllers
- Reactivity: Automatically update the display of model state when the value changes
## The View Part of MVC
- Responsible for rendering a response in a target payload format (HTML, XML, JSON, text)
	- It only reads model state to project a view of the model to the user
	- View layer must not change the state of the model
## View Layer - Templates
- Benefit is the straightforward simplicity
- Disadvantage is potential coupling, hardwiring of a layout
- Pros
	- Still SOC
	- AJAX friendly
	- Let each role stick to what it's good at
	- UI now started with the markup, not the other way around
- Cons
	- Not a lot of layout flexibility, integrated with CSS
	- Proprietary template scripting languages lead to lock in
# The Vue Framework
- Lightweight frontend Javascript framework for web app development
- Build chain approach
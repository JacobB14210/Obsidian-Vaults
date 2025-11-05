# UI Systems in Unity
## UI Toolkit
### Visual Tree
- Visual elements are ordered into hierarchy tree with parent-child relationships
- VisualElement: This class is the base for all nodes in the visual tree
	- Contains properties such as styles, layout data, and event handlers
- Event callbacks can be used to modify the behavior of a visual element
- Draw order: Follows a depth first search
	- Top visual element
	- First child element of that visual element
	- The child elements of the descendant element
### Controls
- Graphical user interface like a button, label, or check box
- Add it to the visual tree for the UI
- Interactions
	- Change the control value
	- Register a callback: Controls that have properties send an event if the value changes
		- Register a callback to receive this event
	- Apply data binding
### The Layout Engine
- Positions visual elements based on layout and styling properties
- Default behaviors
	- Container distributes its children vertically
	- Position of a container rectangle includes its children rectangles
	- Visual element with text uses the text size in its size calculations
- Best practices
	- Set width and height to define the size of element
	- flexGrow: Assign flexible size to an element
	- flexDirection: Property to row to switch to a horizontal layout
	- Use relative positioning to offset an element based on its original layout position
### Event System
- System includes a dispatcher, a handler, a synthesizer, and a library of event types
- Dispatch events: Event system listens to events and dispatches them to visual elements
	- Trickles down: Events sent to elements during the trickle down phase
	- Bubbles up: Events sent to elements during the bubble up phase
	- Cancellable: Events that can have their default action execution cancelled, stopped or prevented
### Data Binding System
- Use data binding to synchronize values between a property and a specific visual element
	- So you don't need to write event handlers when the value changes in the UI
### Unity UI and Immediate Mode GUI
- Unity UI: GameObject based UI system that uses components and the Game View to arrange, position, and style user interfaces
- Immediate Mode GUI: Code driven GUI system
	- Not normally intended to be used for normal in game user interfaces that players might use and interact with
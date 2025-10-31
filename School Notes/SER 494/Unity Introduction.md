# Unity Interface
- Scene: Single space where objects exists
- Assets: File within your game
	- Assets don't have instances
	- They are class definitions
- Scene Hierarchy: Shows all game objects within the scene
# Scripting in Unity
- "Using" is identical to import from java
- ":" is identical to extends from java
- Script must extend MonoBehavior to attach a script to an object
- Scripts attached to objects will happen in real time
## Start Method
- Called when script is first activated
	- Mostly for when scene loads
	- Object could spawn
	- Script can be disabled
- Only called once per script lifetime
- There is also another method called Awake
	- Called before Start, called even if the component is disabled
- There is also OnEnable
	- Works like Start, but called every time the component is enabled
## Update Method
- Called once per frame
	- 60 frames a second
- For anything that runs continuously
- Not a great place to run timers, though good to start them

```c#
public class ExampleScript : MonoBehavior {
	void Start() { // Start is called before first frame
	}
	
	void Update() { // Update is called every frame
		Debug.Log("Error message to consol"); // Log a message into the console
		Debug.LogWarning("This logs a message that will have yellow warning next to it");
		Debug.LogError("This will be an error in the console. The script will keep running");
	}
}
```
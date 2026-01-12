# GameObjects and Components
- GameObject: object instance with a physical location
	- Scene is composed of objects
	- Add behaviors to objects
	- A GameObject can hold any number of behaviors or traits
		- Generally speaking behaviors mean scripts
		- Traits mean physical characteristics like a mesh or texture
- Transform component: Holds X, Y, Z (Absolute position), rotation, scale
	- Trait that all GameObjects have
	- Physical trait of the object
- Special Circumstance - Empty GameObjects
	- Removes object components except for transform
- Prefabs
	- Template of a configuration to make more instances of it later
		- Creating a class
	- When editing you edit all instances
- Components
	- Again, a GameObject can have any number of components on it
	- Public or serialized fields in scripts can be edited on instances they are attached to
	- Components are again member variable objects held by the object
	- They can be accessed in scripts for making changes at run time
# GameObjects and Transform Scripting
## Interacting with Other Components
### Requiring Components
- Enforce required components
	- Can only do this for the same object
	- So you don't have to check for null
- Required component is added automatically if not provided 

```c#
// Make sure the script is attached to a component with a rigid body
[RequireComponent(typeof(Rigidbody))]
public class GameObjectsExamples : MonoBehaviour {
}
```
### Calling Method on Other Components
- Can treat it like any regular object reference
	- Call any public methods, or variables

```c#
exmpleComponent = player.GetComponent<ExampleComponent>();
exampleComponent.test();
```

### Sending Messages to Other Objects
- When message to a GameObject is sent every component with method name will run
	- Can pass a parameter
- RequireReceiver will throw an error message if no methods run
- BrodcastMessage: Works the same but sends it to all child GameObjects

```c#
private const string METHOD_NAME = "SetActive";
private const bool PARAMETER_NAME = false;

void start() {
	if(player is null) {
		player = GameObject.Find("Player");
	}
	player.SendMessage(METHOD_NAME, PARAMETER_NAME, SendMessageOptions.RequireReceiver);
}
```

## Changing the Transform
- Can tell transform to set a position or set the transform to move itself
- Example will move object 1 every frame

```c#
public void Update() {
	transform.Translate(new Vector3(1.0f, 0.0f, 0.0.f));
}
```

## Player Input
### Getting Player Input
- Check for player input in update method
- Types of key inputs
	- GetKey: Continuous holding
	- GetKeyDown: Frame it was first pressed
	- GetMouseButton: Same versions as for keys
		- Requires an int paramenter for which button

```c#
public void Update() {
	if(Input.GetKey(KeyCode.A)) {
		Debug.Log("The Player is pressing A!");
	}
}
```
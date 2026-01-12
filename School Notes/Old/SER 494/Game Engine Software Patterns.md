- Software Pattern: A pattern in software is a common way of writing code
# Software Factories

```c#
public class ExampleFactoryObject { // Object to create
	public ExampleFactoryObject() {
	
	}
}
```

```c#
public static class ExampleFactory { // Factory to create objects
	public static ExampleFactoryObject getExampleObject() {
		return new ExampleFactoryObject();
	}
}
```

## Simple Usage
```c#
public class ExampleFactoryUse : MonoBehavior {
	public void Start() {
		ExampleFactoryObject example = ExampleFactory.getExampleObject();
	}
}
```

## With parameters
```c#
public static class ExampleFactory {
	private const int DEFAULT = 50;
	
	public static ExampleFactoryObject getExampleObject(int num = DEFAULT) {
		retur new ExampleFactoryObject(num);
	}
}
```

# Inheritance and Abstraction
## Inheritance
- Object is declared as a child of another object giving it all public characteristics of the parent
- Keep a list of objects in every form
	- Use operations with for each loop

```c#
public abstract class InheritanceExample {
	private int speed;
	
	public abstract void takeDamage();
	
	public void move(int newSpeed) {
		speed = newSpeed;
	}
}
```

## Interfaces
- Define what methods need to be implemented but not how

```c#
public interface InterfaceExample {
	public Transform getLocationPlayerWasLastSpottedAt();
	public bool getAlertedState();
	public void increaThreatLevel();
}
```

# GameObject Creation and Destruction
## Making GameObjects
- Clones an object reference
- Be default object is created at (0,0,0) with no rotation or scale
	- Each can be passed through to change it
	- Have factory initiate

```c#
public class GameObjectCreationExample : MonoBehavior {
	[SerializedField]
	private GameObject prefabToClone;
	
	public void start() {
		if(prefabToClone is not null) {
			GameObject gameObject = Instantiate(prefabToClone);
		}
	}
}
```

## Destroying GameObjects
- Call destroy
	- Leaving it there after not being used takes of resources
- Can also use:
	- DestoryImmediate (Just use regular Destory)
	- DestroyObject: Deprecated

```c#
public class GamObjectDestructionExample : MonoBehavior {
	[SerializeField]
	private int limit;
	[SerializeField]
	private GameObject target;
	
	public void Update() {
		if(limit <= 0) {
			Destory(target);
		}
	}
}
```
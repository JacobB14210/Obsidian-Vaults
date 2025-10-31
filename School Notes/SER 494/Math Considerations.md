# Vectors and Translating
## Direction On All Axes
- Vectors: Dictates a magnitude and direction
- 3d vector is represented by the Vector3 class
	- Contains 3 floating point numbers
## Examples of Vector Creation
```c#
public class VectorExamples: MonoBehaviour {
	[SerializeField]
	private Vector3 example1;
	
	public void start() {
		example1 = new Vector3(0.0f, 0.0f, 0.0f);
		example.x = 1.0f;
		example.Set(1.0f, 1.0f, 1.0f);
		Vector3 example2 = Vector3.zero;
		transform.Translate(new Vector3(5.0f, 0.0f, 1.0f));
	}
}
```
## More on Vectors
- Unity  vectors are mutable
- Can save it to a variable if vector is used multiple times
- Vector3Int is used for int values instead of floats
	- Recommend against this because transform uses float values
- Vector2 is the same thing but for 2d
# Rotations
## Matrices
- Take a 4x4 matrix and put desired rotations values along the diagonal
	- Last value would be a 1 to normalize the matrix
- Or multiply two matrices to get new rotation values
	- Our rotation times current rotation
- Matrix4x4 is a built in class for handling matrices
## Quaternions
- Quaternion form: a + bi + cj + dk
	- i, j, and k are all imaginary
- When building a quaternion first three numbers are axes and the last is the 1
```c#
public class QuaternionExample : MonoBehaviour {
	[SerializeField]
	private Quaternion quaternion;
	
	public void Start() {
		quaternion.Set(0.0f, 90.0f, 0.0f, 1.0f);
		transform.rotation = quaternion;
		Vector3 understandableRotation = transform.eulerAngles;
		transform.Rotate(new Vector3(0.0f, 90.0f, 0.0f));
	}
}
```

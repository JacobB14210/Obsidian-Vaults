# Lighting
- If an obstruction between the light source, ad the object that obscures part of the light
	- Figure out shadows
- Want to do something fancier with lighting than just static lighting
	- Different types of lighting
## Types of Lights
- Point light: Light shines from a single point in all directions
- Spotlight: A point light that shines within a cone of a specified radius in a given direction
	- Good for flash light or a lighthouse with a rotation script
- Area Light: Square or circle that emits light in one direction
	- Great for fluorescent lights or the glow of a monitor
- Directional Light: Applies light uniformly to the scene from a given direction without diminishing
	- Outdoor scenes with the sun
## Light Settings
- Spotlight has a slider for the angle of the cone
- Shadow type
	- None
	- Hard
	- Soft
- Emission: Change the color and intensity of the light
	- Intensity is not the same as range
- Light cookie: Apply an image to the shadows from this light
	- Underwater effect
- Culling Mash: Define which layers the light applies
## Light Mode
- Default is runtime: Lighting is calculated at runtime
	- For things that move, or want to apply effect through scripting
- Baked: Calculates lighting ahead of time and loads data from the disk when light is needed
	- Super cheap at run time, but static and immovable
	- Used for scenery
- Mixed: Baked that can be edited at runtime
	- Costs more CPU than baked, and more memory in runtime
## Shadows
- Handles shadow with shadow map
	- Unity makes a projection of what the light would be able to illuminate
	- Take higher of the width or height of the projection as the size
	- Result is clamped to a maximum size and then applied to the camera render
- Point lights use cubemap for shadows
	- All six sides need to be in memory at once
	- Have lower limit on size
# Collision Detection

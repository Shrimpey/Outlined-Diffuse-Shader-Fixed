# Outlined Diffuse Shader Fixed for Unity 5.6
This is a fixed version of diffused outline shader from http://wiki.unity3d.com/index.php/Outlined_Diffuse_3
It should be working fine in Unity 5.6 and above.

# Important update:
**A new version of the outline shader is available, go to: https://github.com/Shrimpey/UltimateOutline
Use the updated shader, come back here only if you find it to be working weirdly on your custom models and try some of the ones mentioned below.**

**Guide:**
I suggest you trying **UniformOutline.shader** and then **CustomOutline.shader**. They should work fine for simple objects/complex objects with proper origin. If they fail - try out the **RegularOutline.shader**. The rest of the shaders are for really specyfic purposes, so unless you know what you're doing you probably shouldn't be using them :)

**Showcase:**
Download **OutlineShowcase.unitypackage** and import it to Unity project to see RegularOutline, CustomOutline and UniformOutline shaders in action.

**Shaders:**

# RegularOutline.shader
**RegularOutline.shader** - Just an updated version of the shader from the wiki page, may still work in weird ways => if so, use custom one.
![Regular Outline](/images/standard.PNG?raw=true "Regular Outline")
**Usage**: Curved shapes/thin outlines.
**Problems**: Weird shapes on hard edges.

---
# CustomOutline.shader
**CustomOutline.shader** - My personal take on the outline shader. It increases the scale of the vertices instead of working with normals. 
![Custom Outline](/images/custom.PNG?raw=true "Custom Outline")
**Usage**: All shapes
**Problems**: Possible clipping on really thick edges/weird offsets if model's origin is not in center

---
# UniformOutline.shader
**UniformOutline.shader** - Made from scratch, works just like CustomOutline except the scaling is more uniform - width of the outline should be more consistent on irregular meshes (easy to notice when comparing the wheels of the cart from the image below to the Custom Outline shader image). 

![Uniform Outline](/images/Uniform.PNG?raw=true "Uniform Outline")

**Usage**: All shapes
**Problems**: Same as in Custom Outline, less overlaying, more angled distortions.

---
# CustomOutline-CameraIndependent.shader
**CustomOutline-CameraIndependent.shader** - Same as custom one, but the outline is the same width despite the distance to the camera. 

![Camera Independend Close](/images/camera.PNG?raw=true "Camera Independend Close")
![Camera Independend Far](/images/camera2.PNG?raw=true "Camera Independend Far")

**Usage**: Same sized outline on perspective camera.
**Problems**: Weird shapes on complex objects.

---
# CustomOutline-ConstantWidth.shader
**CustomOutline-ConstantWidth.shader** - Same as custom one, but the outline is constant width despite the camera zoom.

![Constant Width Zoomed In](/images/zoom2.PNG?raw=true "Constant Width Zoomed In")
![Constant Width Zoomed Out](/images/zoom.PNG?raw=true "Constant Width Zoomed Out")

**Usage**: Same outline width despite the camera's zoom (ortho/perspective)
**Problems**: Clipping on thick outlines on complex shapes.

---


*UPDATE 03.09.2017 - Added camera independent version of custom shader*

*UPDATE 04.09.2017 - Added constant size version of custom shader | updated README to include images*

*UPDATE 12.09.2017 - Added uniform outline shader*

*UPDATE 23.12.2017 - Fixed some minor issues with custom, regular and uniform shaders | added showcase unity package*

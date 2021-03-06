---
title: "Glossary"
---


<!-- MathJax Support -->
<style TYPE="text/css">
code.has-jax {font: inherit; font-size: 100%; background: inherit; border: inherit;}
</style>
<script type="text/x-mathjax-config">
MathJax.Hub.Config({
    tex2jax: {
        inlineMath: [['$','$'], ['\\(','\\)']],
        skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'] // removed 'code' entry
    }
});
MathJax.Hub.Queue(function() {
    var all = MathJax.Hub.getAllJax(), i;
    for(i = 0; i < all.length; i += 1) {
        all[i].SourceElement().parentNode.className += ' has-jax';
    }
});
</script>
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

This is a glossary of some common terms used in computer graphics:

<!-- Checkbox Tutorial: https://lokesh-coder.github.io/pretty-checkbox/ -->
<!-- Include Checkbox CSS -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/pretty-checkbox@3.0/dist/pretty-checkbox.min.css">

<fieldset data-role="controlgroup" data-type="horizontal">
<legend>Select all that you would like to display:</legend>
  <div class="pretty p-default p-thick p-pulse">
        <input type="checkbox" id="Course" class="Course" checked/>
        <div class="state">
            <label>Course Related</label>
        </div>
  </div>
  <div class="pretty p-default p-thick p-pulse">
        <input type="checkbox" id="Extra" class="Extra" checked/>
        <div class="state">
            <label>Extra</label>
        </div>
  </div>
  <!-- <label for="blue">VR/AR</label>
  <input type="checkbox" name="favcolor" class='XR' id="XR" value="VR/AR" checked> -->
</fieldset>



<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
<script>
$(document).ready(function () {
    $('.Course').change(function () {
        if (this.checked) $(".course").fadeIn();
        else $(".course").fadeOut();

    });
    $('.Extra').change(function () {
        if (this.checked) $('.extra').fadeIn();
        else $('.extra').fadeOut();

    });
    // $('.XR').change(function () {
    //     if (this.checked) $('.xrdisplay').fadeIn();
    //     else $('.xrdisplay').fadeOut();

    // });
});
</script>

<br>
<div>
<h3>
{% for element in site.data.glossary %}{% unless element.tag %}
<a href="#{{element.name}}">{{element.name}}</a>&nbsp;&nbsp;
{% endunless %}{% endfor %}
</h3>
</div>

{% for element in site.data.glossary %}
{% if element.tag %}
  <div id="{{element.id}}" class="{{element.tag}}">
    <h4 id="{{element.name}}"><strong>{{element.name}}</strong></h4>
    <p>{{element.definition}}</p>
    <hr>
  </div>
{% else %}
  <div>
    <h3 id="{{element.name}}"><strong>{{element.name}}</strong></h3>
  </div>
{% endif %}
{% endfor %}

<!-- ### **0-9**

### **A**

#### **Affine transform** 

A transform that preserves parallel lines. That is, when the transform is applied to a pair of lines that are parallel, then the resulting transformed lines are also parallel. An affine transform,`$T$`, has the property that the transform of the line segment between a point`$(x_1,y_1)$` and a point`$(x_2,y_2)$` is the line between the points`$T(x_1,y_1)$` and`$T(x_2,y_2)$`. Effectively, the transform of a line segment can be computed just by transforming its two endpoints. This makes affine transforms very efficient for computer graphics. Any affine transform can be represented as a composition of rotations, translations, and scalings.


#### **Aliasing**

The visual misrepresentation that occurs when an image or model contains more detail than the display device’s resolution can present. 

#### **Alpha blending**

The process of combining a translucent foreground color with a background color, thereby producing a new blended color. The degree of the foreground color's translucency may range from completely transparent to completely opaque.

#### **Alpha channel**

An additional image channel (e.g. extending an RGB image) or standalone channel controlling Alpha blending. This is the fourth channel in RGBA color space.

#### **Ambient color**

A material property that represents the proportion of ambient light in the environment that is reflected by a surface.

#### **Ambient light**

Directionless light that exists in an environment but does not seem to come from a particular source in the environment. An approximation for light that has been reflected so many times that its original source can't be identified. Ambient light illuminates all objects in a scene equally.

#### **Anchor Point**

Anchor points allow the user to manipulate a path’s shape or direction by clicking the point and moving it in a direction. They are used in various design tools and appear along the beginning of a path, at every curve, and at the end of a path. You can also add or subtract anchor points on a path.

#### **Animation**

A technique that presents a logical sequence of images in such a manner as to create an illusion of motion. 

#### **Aspect Ratio**

The ratio of the height to the width of a rectangle such as is found in a display surface, window, viewport, or character space. 

#### **Antialiasing**

A technique that reduces the visual effects of aliasing. 

### **B**

#### **Back face culling**

Back face culling is a type of culling where the triangles/ploygons pointing away from the camera/viewpoint (i.e. back faces) are not considered for rendering/drawing.

#### **Back face**

One of the two sides of a polygon in 3D. A polygon has two sides. One is taken to be the front face, and the other is the back face. In OpenGL, the difference is determined by the order in which the vertices of the polygon are enumerated. The default is that, seen from the back, the vertices are enumerated in clockwise order around the polygon.

#### **Barycentric coordinates**

A coordinate system on a triangle in which a point is written as a linear combination of the vertices of the triangle, that is,`$a*A+b*B+c*C$`, where`$A$`,`$B$`, and`$C$` are the vertices and`$a$`,`$b$`, and`$c$` are numbers. Any point in the triangle can be written in this form where the coefficients`$a$`,`$b$`, and`$c$` have values in the range 0 to 1 and`$a+b+c = 1$`.

#### **Bezier curve**

A smooth curve between two points defined by parametric polynomial equations. A cubic Bezier curve segment is defined by its two endpoints`$P_1$` and`$P_2$` and by two control points`$C_1$` and`$C_2$`. The tangent to the curve (its direction and speed) at`$P_1$` is given by the line from`$P_1$` to`$C_1$`. The tangent vector to the curve at`$P_2$` is given by the line from`$C_2$` to`$P_2$`. A quadratic Bezier curve is defined by its two endpoints and a single control point`$C$`. The tangent at each endpoint is the line between that endpoint and`$C$`.

#### **Billboards**

Billboards are textured rectangles that are transformed such that they always appear parallel to the view plane. Thus, they are similar to billboards along highways in that they are rotated for best visibility. However, they are different from highway billboards since they are dynamically rotated to always offer best visibility.

#### **Bitmap Image**

A bitmap (or raster) image is one of the two major graphic types (the other being vector image). Bitmap-based images are comprised of pixels in a grid. Each pixel or "bit" in the image contains information about the color to be displayed. Bitmap images have a fixed resolution and cannot be resized without losing image quality. 

#### **BRDF (Bidirectional Reflectance Distribution Function)**

A BRDF describes the reflectance properties of a surface by specifying the amount of radiance incident from one direction that is reflected into another direction, with respect to the surface normal. The main characteristics of a physically plausible BRDF are the symmetry between incident and reflected directions (Helmholtz reciprocity) and that the total reflected power for a given direction of incident radiation is less than or equal to the energy of the incident light (Energy conservation).

#### **Bresenham's line algorithm**

A specific algorithm for deciding which pixels to color to recodesent a geometric line segment, using only integer arithmetic. The algorithm can be implemented very efficiently in computer hardware.

#### **Brightness**

A measure of the visible light intensity of the image displayed on the surface of a display device. 

#### **BSDF (Bidirectional Scattering Distribution Function)**

A generalization of the idea of "material" in 3D graphics. A BSDF gives the probability that a light ray that arrives at point of space from one direction will leave that point heading in a another direction. The probability is a function of the two directions, the point, and the wavelength of the light. One kind of scattering is reflection of light from a surface. For that case, the term BRDF (Bidirectional Reflectance Distribution Function) is used.

#### **Bump Mapping**

Using a texture to modify the normal vectors on a surface, to give the appearance of variations in height without actually modifying the geometry of the surface.

### **C**

#### **Camera**

In 3D computer graphics, an object that combines the projection and viewing transforms into an abstraction that imitates a physical camera or eye.

#### **Clipping**

A computer graphics technique in which display elements lying totally outside a view area are made invisible and display elements lying partially inside a view area are scissored to remove the parts outside the view area before they are mapped to the display image.

#### **Color Buffer**

In OpenGL, the region of memory that holds the color data for the image. It acts as the drawing surface where images are rendered.

#### **Color channels**

The set of channels in a bitmap image representing the visible color components, i.e. distinct from the alpha channel or other information.

#### **Color Gamut**

The color gamut of a display device, such as a printer or computer screen, is the set of colors that can be displayed by the device.

#### **CMYK**

Stands for **C**yan, **M**agenta, **Y**ellow, and **K**ey color (aka — black);  this color model (also called process color, four color) is a subtractive color model  used in color printing.

#### **Compute API**

An API for efficiently processing large amounts of data.

#### **Computer Shaders**

Programs that run on the graphics card, outside of the normal rendering pipeline. They can be used for massively parallel GPGPU algorithms, or to accelerate parts of game rendering.

#### **Contrast**

The relationship between the highest and lowest intensity levels of a display image, usually expressed as
the ratio of light to dark.

#### **Control Point**

A point that does not lie on the curve but that is used to help control the shape of the curve. For example, a control point for a Bezier curve segment is used to specify the tangent vector (direction and speed) of the curve at an endpoint.

#### **Cubemap Texture**

A texture made up of six images, one for each of the directions positive x, negative x, positive y, negative y, positive z, and negative z. The images are intended to include everything that can be seen from a given point. Cubemap textures are used for environment mapping and skyboxes.


### **D**


#### **Deferred Shading**

A multi-pass rendering technique where a first pass processes the geometry and saves relevant information such as transformed coordinates, normal vectors, and material properties. The data can be stored in textures, which are called "geometry buffers" or "G-buffers" in this context. Lighting and other effects can then be computed in additional passes, using the pre-computed information from the geometry buffers instead of re-computing it for each pass.

#### **Delaunay triangulation**

A method for generating an efficient triangulation between a set of vertices in a plane.

#### **Depth Buffer**

A bitmap image holding depth values (either a Z buffer or a W buffer), used for visible surface determination, during rasterization of 3D scenes.

#### **Depth Map**

A image or texture map holding depth values. At each pixel corresponding to a depth map, we have an associated depth value. Similar to a height map or displacement map, but usually associated with a projection.

#### **Depth Value**

A value in a depth map representing a distance perpendicular to the space of an image.

#### **Diffuse Color**

Diffuse color is the most instinctive meaning of the color of an object. It is that essential color that the object reveals under pure white light. It is perceived as the color of the object itself rather than a reflection of the light. *Contrast with luminous color and specular highlights*

#### **Diffuse Reflection**

Diffuse reflection is the reflection of light from a surface such that a ray incident on the surface is scattered at many angles rather than at just one angle as in the case of specular reflection. An ideal diffuse reflecting surface is said to exhibit Lambertian reflection, meaning that there is equal luminance when viewed from all directions lying in the half-space adjacent to the surface.

#### **Directional Light**

A light source whose light rays are parallel, all arriving from the same direction. Can be considered to be a light source at an effectively infinite distance. Also called a "sun," since the Sun is an example of a directional light source.

#### **Displacement Mapping**

Displacement mapping is a technique for adding geometric detail to surfaces at render time. In contrast with bump mapping, which works by just changing the surface normal to create the illusion of surface detail, displacement mapping modifies the surface itself.

#### **Double Buffering**

A graphics technique in which an image is drawn off-screen, in a region of memory called an off-screen buffer or "back buffer." When the image is drawn, it can be copied to the buffer that represents the contents of the screen, which is also known as the "front buffer." In true double buffering, the image doesn't have to be copied; instead, the buffers can be "swapped" so that the back buffer becomes the front buffer, and the front buffer becomes the back buffer.


### **E**

#### **Eucledian Transform**

A transform that preserves distances and angles. A Euclidean transform represents a "rigid motion". That is, the transform of an object is an exact copy of the object, with the same size and shape. Any Euclidean transform can be represented as a composition of rotations and translations.

#### **Euler Angles**

Euler angles are the angles of rotation of a three-dimensional coordinate frame. A rotation of Euler angles is represented as a matrix of trigonometric functions of the angles.

#### **Eye Coordinates**

The coordinate system on 3D space defined by the viewer. In eye coordinates in OpenGL (by default), the viewer is located at the origin, looking in the direction of the negative z-axis, with the positive y-axis pointing upwards, and the positive x-axis pointing to the right. The modelview transformation maps objects into the eye coordinate system, and the projection transform maps eye coordinates to clip coordinates.

### **F**

#### **Fixed-function pipeline**

A hardware rendering pipeline without shaders, composed entirely of fixed function units. A limited number of functions may be controlled by render states.

#### **Flat Shading**

A lighting computation for the faces of a polygon or polygonal mesh that uses the same normal vector at each point in the polygon, giving the polygon a flat or faceted appearance.

#### **Fragment Shader**

A shader program that will be executed once for each pixel in a primitive. A fragment shader must compute a color for the pixel, or discard it. Fragment shaders are also called pixel shaders.

#### **Frame Buffer**

A region of memory that contains color data for a digital image. Most often refers to the memory containing the image that appears on the computer's screen.

#### **Front Face**

One of the two sides of a polygon in 3D. A polygon has two sides. One is taken to be the front face, and the other is the back face. In OpenGL, the difference is determined by the order in which the vertices of the polygon are enumerated. The default is that, seen from the front, the vertices are enumerated in counterclockwise order around the polygon.

#### **Frustum**

A truncated pyramid; that is, a pyramid from which the top has been cut off. In OpenGL, the view volume for a perspective projection is a frustum.

### **G**

#### **G-buffer**

A screen space representation of geometry and material information, generated by an intermediate rendering pass in deferred shading rendering pipelines.

#### **Geometric Modelling**

Creating a scene by specifying the geometric objects contained in the scene, together with geometric transforms to be applied to them and attributes that determine their appearance.

#### **Geometric Primitives**

Geometric objects in a graphics system, such as OpenGL, that are not made up of simpler objects. Examples in OpenGL include points, lines, and triangles, but the set of available primitives depends on the graphics system.

#### **Ghost/Ghosting**

The residue of an old image, displayed at the same time as a new image, that occurs when the persistence is longer than the refresh rate. 

#### **GLSL**

OpenGL Shader Language, the programming languauge that is used to write shader programs for use with OpenGL.

#### **GLU**

The OpenGL Utility library. Defines several functions for use with older versions of OpenGL, including gluPerspective and gluLookAt. Not to be confused with GLUT. GLU is a standard part of OpenGL.

#### **GLUT**

The OpenGL Utility Toolkit: A platform-independent library for writing OpenGL applications. OpenGL does not include support for windows or events. GLUT adds such support. It also has functions for drawing 3D shapes such as spheres and polyhedra (not to mention a teapot). GLUT is written in the C programming language and is used with the C API for OpenGL. A newer, and somewhat improved, version of the toolkit named "FreeGLUT" is commonly used in place of the original version.

#### **Gouraud Shading**

A technique for shading a three-dimensional solid object by interpolating the light intensities at the vertices of each polygon face, resulting in smooth shading.

#### **GPU**

Graphics Processing Unit, a computer hardware component that performs graphical computations that create and manipulate images. Operations such as drawing a line on the screen or rendering a 3D image are done in the GPU, which is optimized to perform such operations very quickly.

#### **Graphics Language**

A programming language that produces display data. 

#### **Graphical Shader**

A shader associated with the rendering pipeline; not a compute shader.

#### **Grayscale**

Refers to a color scheme or image in which each color is a shade of gray (where the term "shade of gray" here includes black and white). Typically, 256 shades of gray are used. Grayscale is also called "monochrome."

#### **GUI (Graphical User Interface)**

A user interface for a program where the user interacts with the program using components such as windows, menus, buttons, and text-input boxes.

### **H**

#### **Hidden Surface Problem**

The problem in 3D graphics of deciding which object is visible at each pixel in an image. When one object is behind another object from the point of view of the viewer, only the front object should appear in the image. A rendering algorithm for 3D graphics must satisfy this constraint. Algorithms that solve the hidden surface problem include the painter's algorithm and the Z-buffer test algorithm.

#### **Hierarchical Modeling**

Creating complex geometric models in a hierarchical fashion, starting with geometric primitives, combining them into components that can then be further combined into more complex components, and so on.

#### **Homogeneous Coordinates**

A way of representing n-dimensional vectors as `$(n+1)$`-dimensional vectors where two `$(n+1)$`-dimensional vectors represent the same `$n$`-dimensional vector if they differ by a scalar multiple. In 3D, for example, if `$w$` is not zero, then the homogeneous coordinates `$(x,y,z,w)$` are equivalent to homogeneous coordinates `$(x/w,y/w,z/w,1)$`, since they differ by multiplication by the scalar `$w$`. Both sets of coordinates represent the 3D vector `$(x/w,y/w,z/w)$`

#### **HSV Color**

A color specified by three numbers namely, the hue, saturation, and value. The hue represents the basic color. The saturation is the purity of the color, with a saturation value of zero producing a shade of gray, that is a color with no actual hue at all. The value represents the brightness of the color, with a value of zero giving black. (Value is also called brightness, and the name HSB is sometimes used instead of HSV.)

### **I**

#### **Identity Transform**

A transform that has no effect on its argument. For example, the identity transform in 2D is given by the formula `$I(x,y) = (x,y)$`. The identity transform `$I$` has the property that if `$T$` is any transform, then `$I$` followed by `$T$` is the same as `$T$`, and `$T$` followed by `$I$` is the same as `$T$`.

#### **Image Texture**

An image that is applied to a surface as a texture, so that it looks at if the image is "painted" onto the surface.

#### **Interpolation**

Given values for some quantity at certain reference points, computing a value for that quantity at other points by some kind of averaging applied to the values at the reference points.

### **J**


### **K**

#### **Keyframe Animation**

An animation technique in which the value of some quantity is given explicitly only at certain times during the animation. The times when the quantity is specified are called keyframes. Between keyframes, the value of the quantity is obtained by interpolating between the values specified for the keyframes.

### **L**

#### **Lambert Shading**

A technique for computing pixel colors on a primitive using a lighting equation that takes into account ambient and diffuse reflection. In Lambert shading, the lighting equation is applied only at the vertices of the primitive. Color values for pixels in the primitive are calculated by interpolating the values that were computed for the vertices. 

#### **Lighting Equation**

The equation that is used in OpenGL to compute the visible color of a point on a surface from the material properties of the surface, the normal vector for that point, the direction to the viewer, the ambient light level, and the direction and intensity of light sources.

#### **Light field**

Light field is a vector function that describes the amount of light flowing in every direction through every point in space. The direction of each ray is given by the 5D plenoptic function, and the magnitude of each ray is given by the radiance. It may be captured using multiple cameras (e.g. light stage), or rendered from a 3D model by ray tracing.

#### **Linear Transformation**

A function from one vector space to another that preserves vector addition and multiplication by constants. Linear transformations can be represented by matrices. In computer graphics, they are used to implement geometric operations such as rotation and translation.

#### **Lissqjous figures**

A pattern of two mutually orthogonal sets of curve forms, used to generate characters or curves, or for testing purposes.

#### **Luminance**

A quantity representing the perceived brightness of a color. For an RGB color, it is a weighted average of the red, green, and blue components of the color. The usual formula is `$0.3*red + 0.59*green + 0.11*blue$`.

### **M**

#### **Marching cubes**

Marching cubes is a computer graphics algorithm, published in the 1987 SIGGRAPH proceedings by Lorensen and Cline, for extracting a polygonal mesh of an isosurface from a three-dimensional discrete scalar field (sometimes called a voxel). This paper is one of the most cited papers in the computer graphics field.

#### **Magnification filter**

An operation that is used when applying a texture to an object, when the texture has to be stretched to fit the object. For an image texture, a magnification filter is applied to compute the color of a pixel when that pixel covers just a fraction of a pixel in the image.

#### **Material**

The properties of an object that determine how that object interacts with light in the environment. Material properties in OpenGL include, for example, diffuse color, specular color, and shininess.

#### **Mesh**

A group of polygons that, when placed on the surface of a three-dimensional object, visually describes the shape of the exterior surface.

#### **Minification filter**

An operation that is used when applying a texture to an object, when the texture has to be shrunk to fit the object. For an image texture, a minification filter is applied to compute the color of a pixel when that pixel covers several pixels in the image.

#### **Mipmap**

One of a series of reduced-size copies of a texture image, of decreasing width and height. Starting from the original image, each mipmap is obtained by dividing the width and height of the previous image by two (unless it is already 1). The final mimpap is a single pixel. Mipmaps are used for more efficient mapping of the texture image to a surface, when the image has to be shrunk to fit the surface.

#### **Mirroring**

The rotation of one or more display elements one hundred and eighty degrees about an axis in the plane of the display surface.

#### **Modeling transformation**

A transformation that is applied to an object to map that object into the world coordinate system or into the object coordinate system for a more complex, hierarchical object.

#### **Modelview transformation**

In OpenGL, a transform that combines the modeling transform with the viewing transform. That is, it is the composition of the transformation from object coordinates to world coordinates and the transformation from world coordinates to eye coordinates. Because of the equivalence between modeling and viewing transformations, world coordinates are not really meaningful for OpenGL, and only the combined transformation is tracked.

### **N**

#### **Normal vector**

A normal vector to a surface at a point on that surface is a vector that is perpendicular to the surface at that point. Normal vectors to curves are defined similarly. Normal vectors are important for lighting calculations.

### **O**

#### **Occlusion Culling**

Occlusion Culling is a feature that disables rendering of objects when they are not currently seen by the camera because they are obscured (occluded) by other objects.

#### **OpenGL**

A family of computer graphics APIs that is implemented in many graphics hardware devices. There are several versions of the API, and there are implementations, or "bindings" for several different programming languages. Versions of OpenGL for embedded systems such as mobile phones are known as OpenGL ES. WebGL is a version for use on Web pages. OpenGL can be used for 2D as well as for 3D graphics, but it is most commonly associated with 3D.

#### **Object Coordinates**

The coordinate system in which the coordinates for points in an object are originally specified, before they are transformed by any modeling or other transform that will be applied to the object.

#### **Orthographic Projection**

A projection from 3D to 2D that simply discards the z-coordinate. It projects objects along lines that are orthogonal (perpendicular) to the xy-plane. In OpenGL, the view volume for an orthographic projection is a rectangular solid.

### **P**

#### **Painter's Algorithm**

A solution to the hidden surface algorithm that involves drawing the objects in a scene in order from back to front, that is, in decreasing order of distance from the viewer. A disadvantage is that the order is usually not well-defined unless some objects are decomposed into smaller sub-objects. Another issue is that the order of drawing has to change when objects move or when the point of view changes.

#### **Panning**

In computer graphics, the process of moving an entire display image in such a manner that new data appears within the viewport as old data disappears, to give a visual impression of horizontal movement of the image. Note: The term panning is sometimes used to mean horizontal or vertical movement. *Contrast with Scrolling*.

#### **Parallax**

The apparent displacement of an object as seen from two different points. It is used to simulate a three-dimensional image on a graphical display device. 

#### **Path Tracing**

A rendering algorithm based on the idea of computing all the paths that light could have followed to arrive at the position of a viewer from each direction. Since that is literally impossible, the algorithm traces a random sample of paths and averages the results. As the number of samples increases, the average converges to a very high-quality image.

#### **PBR (Physically Based Rendering)**

A general term encompassing a variety of techniques for rendering materials that look more physically realistic than the materials traditionally used in OpenGL and similar graphics APIs. PBR has recently become common in real-time graphics such as video games.

#### **Perlin Noise**

A technique invented by Ken Perlin in 1983 that is used in the computation of natural-looking procedural textures (He was awarded an Academy award for inventing this technique). A Perlin noise function has numerical inputs (usually 2 or 3) and produces an output number in the range -1.0 to 1.0. The output is pseudo-random, but has some regularity, with features that are similarly sized and regularly distributed, and with variation on several scales.

#### **Perspective Projection**

A projection from 3D to 2D that projects objects along lines radiating out from a viewpoint. A perspective projection attempts to simulate realistic viewing. A perspective projection preserves perspective; that is, objects that are farther from the viewpoint are smaller in the projection. In OpenGL, the view volume for a perspective projection is a frustum, or truncated pyramid. *Contrast with Orthographic Projection*.

#### **Phong Shading**

A technique for computing pixel colors on a primitive using a lighting equation that takes into account ambient, diffuse, and specular reflection. In Phong shading, the lighting equation is applied at each pixel. Normal vectors are specified only at the vertices of the primitive. The normal vector that is used in the lighting equation at a pixel is obtained by interpolating the normal vectors for the vertices. Phong shading is named after Bui Tuong Phong, who developed the theory in the 1970s. *Contrast with Gouraud Shading*.

#### **Projection**

The transformation of an N-dimensional image into an image in less than N dimensions.

#### **Pixel**

A digital image is made up of rows and columns of small rectangles called pixels. To specify a digital image, a color is assigned to each pixel in the image.

#### **Point Cloud**

A surface defined by a collection of vertices without connectivity information.

#### **Polygonal Mesh**

A collection of polygons, where the polygons can be joined together along their edges. A polygonal mesh can represent a polyhedron, or can be used as an approximation for a curved surface. A polygonal mesh can be represented as an indexed face set.

#### **Polyhedron**

A closed 3D figure whose faces, or sides, are polygons. Usually, it is assumed that the faces of a polyhedron do not intersect, except along their edges.

#### **Power-of-two Texture**

A texture image whose width and height are powers of two. In some graphics systems, this is a requirement of any image that is to be used as a texture.

#### **Procedural Texture**

A texture for which the value at a given set of texture coordinates is computed as a mathematical function of the coordinates, as opposed to an image texture where the value is obtained by sampling an image.

#### **Programmable Pipeline**

A graphics processing pipeline in which some of the processing stages can or must be implemented by programs. Data for an image passes through a sequence of processing stages, with the image as the end product. The sequence is called a "pipeline." Programmable pipelines are used in modern GPUs to provide more flexibility and control to the programmer. The programs for a programmable pipeline are known as shaders and are written in a shader programming language such as GLSL.

#### **Projection Transformation**

In 3D graphics, a transformation that maps a scene in 3D space onto a 2D image. In OpenGL, the projection maps the view volume (that is, the region in 3D space that is visible in the image) to clip coordinates, in which the values of x, y, and z range from -1 to 1. The x- and y-coordinates are then mapped to the image, while the z coordinate provides depth information.

### **Q**

#### **Quad**

A quadrilateral, that is a four-sided figure in the plane. OpenGL has the primitives GL_QUADS and GL_QUAD_STRIP for drawing quads, but it assumes without checking that the vertices that are provided are in fact planar and define quadrilaterals that are convex.

#### **Quaternion**

A means of representing rotations in a 4D vector, useful for skeletal animation, with advantages for interpolation compared to euler angles (i.e. not suffering from gimbal lock).

### **R**

#### **Raster Image**

See Bitmap Image

#### **Rasterization**

Rasterisation (or rasterization) is the task of taking an image described in a vector graphics format (shapes) and converting it into a raster image (pixels or dots) for output on a video display or printer, or for storage in a bitmap file format. In normal usage, the term refers to the popular rendering algorithm for displaying 3D models on a computer.

#### **Ray Casting**

The process of following a ray (that is, half of an infinite line) starting at a given point and extending in a given direction, in order to find points of intersection of the ray with objects in a scene. Usually, only the intersection point that is closest to the starting point of the ray is of interest.

#### **Ray Tracing**

A technique for displaying a threedimensional object with shading and shadows, by tracing light rays backward from the viewing position to the light source, on a two-dimensional display surface. 

#### **Real-Time Graphics**

The type of computer graphics that is needed for computer animation or other applications where the images must be rendered quickly, at the time when they are viewed. For computer animation, real-time graphics generally requires the ability to render the scene sixty times per second.

#### **Reflectance**

The amount of light reflected from the surface of a three-dimensional object. This quality is used in rendering three-dimensional objects in computer graphics.

#### **Refractance**

The amount that light rays are bent upon intersecting the surface of a three-dimensional object. This property is used in rendering three-dimensional objects in computer graphics. 

#### **Render-to-texture**

A technique in which the output of a rendering operation is written directly to a texture. In WebGL, render-to-texture can be implemented by attaching the texture as one of the buffers in a framebuffer.

#### **Rendering**

The process of producing a 2D image from a 3D scene description.

#### **RGBA color**

An RGB color—specified by red, green, and blue component values—together with an alpha component. The alpha component is most often take to specify the degree of transparency of the color, with a maximal alpha value giving a fully opaque color.

### **S**

#### **Scaling**

A geometric transform that multiplies each coordinate of a point by a number called the scaling factor. Scaling increases or decreases the size of an object, but also moves its points closer to or farther from the origin. Scaling can be uniform—the same in every direction—or non-uniform—with a different scaling factor in each coordinate direction. A negative scaling factor can be used to apply a reflection.

#### **Scan Conversion**

The process of redefining an image from one that is composed of lines, points, and areas to one that is expressed in an array of pixels. 

#### **Scrolling**

In computer graphics, the process of moving an entire display image in such a manner that new data appears within the viewport as old data disappears, to give a visual impression of vertical movement of the image. Note: The term scrolling is sometimes used to mean vertical or horizontal movement. 

#### **Shading**

Shading is referred as the implementation of illumination model at pixel points or polygon surfaces of the graphics objects. Remember, illumination (lighting) model determines the color of a surface point by simulating some light attributes whereas shading model applies the illumination models at a set of points and colors the whole image.

#### **Shadow Mapping**

A technique for determining which parts of a scene are illuminated and which are in shadow from a given light source. The technique involves rendering the scene from the point of the view of the light source, but uses only the depth buffer from that rendering. The depth buffer is the "shadow map." Along a given direction from the light source, the object that is illuminated by the light is the one that is closest to the light. The distance to that object is essentially encoded in the depth buffer. Objects at greater distance are in shadow.

#### **Shadow Ray**

In the ray tracing algorithm, a ray that is cast from a point on object in the direction of a light source to determine whether that point is illuminated by that light source or is in shadow.

#### **Shear Transform**

A shear transformation in 2D leaves some line, L, fixed, and lines perpendicular to L are "tilted" relative to L by the same angle. Another description is that a line parallel to L is mapped to itself, but is moved by an amount proportional to its distance from L. In 3D, a shear transformation leaves some plane, P, fixed, and it maps a plane parallel to P to itself, but moved by an amount proportional to its distance from P.

#### **Shininess**

A material property that determines the size and sharpness of specular highlights. Also called the "specular exponent" because of the way it is used in lighting calculations. In OpenGL, shininess is a number in the range 0 to 128.

#### **Skybox**

A large cube that surrounds a scene and is textured with images that form a background for that scene, in all directions.

#### **Spatial Hashing**

A form of hashing to accelerate spatial testing e.g. for AI, collision detection, typically using a grid cell index as a key.

#### **Specular Highlight**

Illumination of a surface produced by specular reflection. A specular highlight is seen at points on the surface where the angle from the surface to the viewer is approximately equal to the angle from the surface to a light source.

#### **Specular Light**

Specular light is the white highlight reflection seen on smooth, shinny objects. Specular light is dependent on the direction of the light, the surface normal and the viewer location.

#### **Spline**

A curve defined by polynomial interpolation through control points.

#### **Spotlight**

A light that emits a cone of illumination. A spotlight is similar to a point light in that it has a position in 3D space, and light radiates from that position. However, the light only affects objects that are in the spotlight's cone of illumination.

#### **Sprite**

In computer graphics, a sprite is a two-dimensional image or animation that is integrated into a larger scene.

#### **Subsurface Scattering**

A lighting effect in which light enters a slightly translucent object, is reflected internally one or more times, and then exits the object at a different point. Subsurface scattering contributes to the appearance of materials such as jade, milk, and skin.

#### **SVG (Scalable Vector Graphics)**

An XML language for specifying 2D vector graphics. SVG is a scene description language. It is designed to integrate into web pages.

### **T**

#### **Texel**

A pixel in a texture image.

#### **Texture coordinates**

Refers to the 2D coordinate system `$(u,v)$` on a texture image, or to similar coordinate systems for 1D and 3D textures. Texture coordinates typically range from 0 to 1 both vertically and horizontally, with (0,0) at the lower left corner of the image. The term also refers to coordinates that are given for a surface and that are used to specify how a texture image should be mapped to the surface.

#### **Texture transformation**

A transformation that is applied to texture coordinates before they are used to sample data from a texture. The effect is to translate, rotate, or scale the texture on the surface to which it is applied.

#### **three.js**

A JavaScript library for 3D graphics made by mr.doob and his collegues. The library implements an object-oriented scene graph API. While it is used primarily with WebGL, three.js can also render 3D scenes using the 2D canvas graphics API.

#### **Torus**

A 3D geometric object having the shape of a doughnut (or bagel).

#### **Two-sided Lighting**

An option in OpenGL that allows the back face of a polygon to have different material properties from the front face. Also, when this option is on, the normal vector that is used in lighting calculations for the back face is taken to be the negative of the vector for the front face. (The negative of a vector points in the opposite direction.)

### **U**

#### **Uniform Scaling**

A scaling transformation in which the scaling factors in all directions are the same. Uniform scaling changes the size of an object without distorting its shape.

#### **UV unwrapping**

The process of flattening a 3D model's surface into a flat 2D plane in a contiguous, spatially coherent manner for texture mapping.

#### **UV coordinates**

Coordinates in texture space, assigned as vertex attributes and/or calculated in vertex shaders, used for texture lookup, defining the mapping from texture space to a 3D model surface or any rendering primitive.

### **V**

#### **Vector**

An element of a vector space. Elements of a vector space can be added and can be multiplied by constants. For computer graphics, a vector is just a list or array containing two, three, or four numbers. 

#### **Vector Graphics**

Shape-based graphics in which an image is represented as a collection of vectors. *Contrast with Raster Graphics*.

#### **Vertex**

One of the points that define a geometric primitive, such as the two endpoints of a line segment or the three vertices of a triangle. (The plural is "vertices.") A vertex can be specified in a coordinate system by giving its x and y coordinates in 2D graphics, or its x, y, and z coordinates in 3D graphics.

#### **Vertex Shader**

A shader program that will be executed once for each vertex in a primitive. A vertex shader must compute the vertex coordinates in the clip coordinate system. It can also compute other properties, such as color.

#### **Viewing Transformation**

The transformation in 3D graphics that maps world coordinates to eye coordinates. The viewing transform establishes the position, orientation, and scale of the viewer in the world.

#### **Viewport**

The rectangular area in which the image for 2D or 3D graphics is displayed. The coordinates on the viewport are pixel coordinates, more properly called device coordinates since they are actual physical coordinates on the device where the image is being displayed.

#### **Viewport Transformation**

In OpenGL, the final transformation from clip coordinates to device coordinates. The viewport transformation maps the clipping cube (the cube in 3D given by x, y, and z coordinates in the range from -1 to 1) to the viewport (the rectangle in the drawing surface where the image is rendered).

#### **View Volume**

In OpenGL, the region is 3D space that is visible in the rendered image. For orthographic projections, the view volume is a rectangular solid. For perspective projection, the view volume is a frustum (truncated pyramid).

#### **Voxels**

An extension of pixels into 3 dimensions.

#### **View frustum**

a truncated pyramid enclosing the subset of 3D space that projects onto a 'viewport' (a rectangular region in screen space, usually the entire screen)


### **W**

#### **WebGL**

A 3D graphics API for use on web pages. WebGL programs are written in the JavaScript programming language and display their images in HTML canvas elements. WebGL is based on OpenGL ES, the version of OpenGL for embedded systems, with a few changes to adapt it to the JavaScript language and the Web environment.

#### **Wireframe**

A style of drawing a polyhedron or polygonal mesh in which only the edges are drawn, resulting in an image made up of line segments.

#### **Wireframe rendering**

A rendering of a 3D model displaying only edge connectivity; used in 3D modelling applications for greater interactive speed, and clarity for mesh editing.


### **X**


### **Y**


### **Z**

#### **Z-Buffer/Depth-Buffer Test**

The basic idea is to test the Z-depth of each surface to determine the closest (visible) surface. In this method each surface is processed separately one pixel position at a time across the surface. The depth values for a pixel are compared and the closest (smallest z) surface determines the color to be displayed in the frame buffer.

#### **Zoom**

To display all or part of a graphical display image at a scale different from the scale of the previous image. Note: In zoom in, the scale is larger; in zoom out, the scale is smaller -->

### **References:**

- [Wikipedia](https://en.wikipedia.org/wiki/Glossary_of_computer_graphics) 
- [IEEE](http://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=159476)
- [Autodesk](https://knowledge.autodesk.com)
- [Introduction to Graphics](http://math.hws.edu/graphicsbook/glossary.html)



---
title:  "OpenGL and Shaders"
date:   2018-03-14 21:30:00
categories: text
toc: true
---

<style type="text/css">	
img.img {
    width: 75%;
}
</style>

## **OpenGL**

If this is your first time reading computer graphics then terms like OpenGL and Shaders might be new to you. To explain it, I would use the following diagram:

<center>
<figure>
<img class="img" src="https://mdn.mozillademos.org/files/13334/mdn-games-3d-rendering-pipeline.png" alt="Rendering Pipeline">
<figcaption>Rendering Pipeline (Reference: Mozilla)</figcaption>
</figure>
</center>	

The above image is an image of the rendering pipeline. Rendering refers to the process of producing a 2D image from a 3D scene description. So, whenever we display any scene on our computer screen, the scene undergoes above steps in background before we see the final pixels on our screen. So, to control the different parts of this pipeline we use APIs (application programming interfaces) like OpenGL and to control what happens in the arrows (Refer above image), we use something called as "shaders".

Officially, OpenGL is a family of cross-platform computer graphics APIs that are used to interact with the GPU for rendering. The main advantage of OpenGL is that it is cross-platform (runs on most Operating Systems like Linux, Windows, Mac OSX) and is implemented in most Nvidia and AMD GPUs. There are several versions of the API, and there are implementations, or "bindings" for several different programming languages like C++, Java, Python etc (For the full list refer to this [link](https://www.khronos.org/opengl/wiki/Language_bindings)). Versions of OpenGL for embedded systems such as mobile phones are known as OpenGL ES and versions for use on Web pages are called WebGL. Most CS courses on computer graphics expect students to learn OpenGL or some variant of it as a part of the course.


Besides OpenGL, there are other APIs for rendering like DirectX and Vulkan. DirectX, developed by Microsoft is also supported by almost all Nvidia and AMD GPUs but it isn't cross-platform and runs only on Windows OS. Vulkan is another API developed by [Khronos Group](https://www.khronos.org/) (the same group that maintains OpenGL). It is more recent (the first version of Vulkan was released in 2016) and the main motivation behind Vulkan was to give programmers and game designers more low-level access to hardware/GPU to boost performance and efficiency. This of course comes at a cost of more significant up-front work on developer's part. As per Khronos the Vulkan API, which will complement (and in some cases replace) OpenGL and OpenGL ES.

The main advantage of using these APIs is that a user gets to control almost each and every part of the rendering pipeline and perform necessary optimizations. In the long run, it is always useful to learn atleast one of these APIs (hence most CS courses on computer graphics expect students to learn OpenGL or some variant of it as a part of the course). But, a new user can always use other tools like [three.js](https://threejs.org/) (a wrapper around WebGL granting high level access), Unity3D (game engine) etc to significantly reduce programming effort. For example to create a Facebook 3D post of rotating earth you literally require **0 lines of code** if you use threejs:

<center>
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Creating <a href="https://twitter.com/facebook?ref_src=twsrc%5Etfw">@facebook</a> 3D posts with <a href="https://t.co/jLTyKERwDZ">https://t.co/jLTyKERwDZ</a> <a href="https://t.co/joZJ5jB4Ly">pic.twitter.com/joZJ5jB4Ly</a></p>&mdash; Ricardo Cabello (@mrdoob) <a href="https://twitter.com/mrdoob/status/967110744566153216?ref_src=twsrc%5Etfw">February 23, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</center>

In comparison to this, if you are using C++ version of OpenGL, just to create a rotating Earth, you will need to include a few libraries, link everything, place the camera, light source, sphere and assign texture. Though this might take a lot more time, it gives you more control. 

Hence, in the subsequent subsections I list various resources for OpenGL. Since knowing the tools are also important, my next post is about these tools.

### **Learning OpenGL**

#### **Books**

In my first post, I had listed some books for learning computer graphics. Usually, some of those books also cover OpenGL. [Realtime Rendering](http://www.realtimerendering.com/books.html) has an awesome and updated graphics page with most recent books on Computer Graphics and programming. I would recommend going to their page if you are looking to buy a book on some part of graphics. 

One of the most popular books on OpenGL is [OpenGL SuperBible](https://smile.amazon.com/OpenGL-Superbible-Comprehensive-Tutorial-Reference/dp/0672337479).

#### **Videos**

* [Siggraph 2013 video](https://www.youtube.com/watch?v=6-9XFm7XAT8) on "Introduction to OpenGL" Programming.
* [Sonar Systems](https://www.youtube.com/playlist?list=PLRtjMdoYXLf6zUMDJVRZYV-6g6n62vet8): Nice set of tutorials on Modern OpneGL 3.0+ (Windows as well as Mac environment setup explained). Covers even advance topics like Obj loading etc.
* [MakingGamesWithBen](https://www.youtube.com/playlist?list=PLSPw4ASQYyymu3PfG9gxywSPghnSMiOAW): Tutorials on OpenGL 2D game development.
* [thebennybox](https://www.youtube.com/playlist?list=PLEETnX-uPtBXT9T-hD0Bj31DSnwio-ywh): Tutorials on OpenGL development.
* [ThinMatrix](https://www.youtube.com/playlist?list=PLRIWtICgwaX0u7Rf9zkZhLoLuZVfUksDP): Tutorials on OpenGL-3D game development in Java.

#### **Websites**

Some of the websites with tutorials on OpenGL (Reference: [Awesome page](https://github.com/eug/awesome-opengl#websites) of OpenGL)
* [Learn OpenGL](https://learnopengl.com) by **Joey de Vries**
* [Learning Modern 3D Graphics Programming](https://bitbucket.org/alfonse/gltut/wiki/Home) by **Jason L. McKesson**
* [Light House 3D](http://www.lighthouse3d.com/tutorials/glsl-core-tutorial) by **Light House 3D**
* [Modern OpenGL](http://www.tomdalling.com/blog/category/modern-opengl) by **Tom Dalling**
* [OpenGL Examples](https://github.com/McNopper/OpenGL) by **Norbert Nopper**
* [OpenGL Step by Step](http://ogldev.atspace.co.uk) by **Etay Meiri**
* [OpenGL Tutorial](https://open.gl) by **Alexander Overvoorde**
* [OpenGL Tutorial](http://antongerdelan.net/opengl/index.html) by **Anton Gerdelan**
* [OpenGL Tutorial](http://www.opengl-tutorial.org) by **Bonder Wu**
* [OpenGL Tutorial](http://www.songho.ca/opengl) by **Song Ho Ahn**

### **OpenGL Libraries**

Knowing what libraries to use is also important. It can help save the time spent exploring random libraries with limited support. Some of the widely used OpenGL libraries are (Reference: [Awesome page](https://github.com/eug/awesome-opengl#libraries) of OpenGL):

* [assimp](http://assimp.sourceforge.net) - Portable library to import 3D models in a uniform manner.
* [Bullet](http://bulletphysics.org/wordpress) - It provides state of the art collision detection, soft body and rigid body dynamics.
* [freeGLUT](http://freeglut.sourceforge.net) - Mature library that allows to create/manage windows containing OpenGL contexts.
* [GLFW](http://www.glfw.org) - Modern library for creating/interact windows with OpenGL contexts.
* [GLFM](https://github.com/brackeen/glfm) - Supplies an OpenGL ES context and input events for mobile devices and the web.
* [glm](http://glm.g-truc.net/0.9.6/index.html) - Mathematics library for graphics software based on the GLSL specifications.
* [Magnum](https://github.com/mosra/magnum) - It is a 2D/3D graphics engine for modern OpenGL.
* [MathFu](http://google.github.io/mathfu/) - C++ math library developed primarily for games focused on simplicity and efficiency.
* [Newton](http://newtondynamics.com/forum/newton.php) - It is a cross-platform life-like physics.
* [OGLplus](http://oglplus.org) - Collection of libraries which implement an object-oriented facade over OpenGL.
* [SDL](http://www.libsdl.org) - Designed to provide low level access to multimedia and graphics hardware.
* [SFML](http://www.sfml-dev.org) - Simple interface to ease the development of games and multimedia applications.
* [SOIL](http://www.lonesock.net/soil.html) - Tiny C library used primarily for uploading textures into OpenGL. (see [SOIL2](https://bitbucket.org/SpartanJ/soil2))
* [Pangolin](https://github.com/stevenlovegrove/Pangolin) - Lightweight portable rapid development library for managing OpenGL display / interaction and abstracting video input.

### **OpenGL Profile Loaders**

* [gl3w](https://github.com/skaslev/gl3w) - Simple OpenGL core profile loader.
* [glad](https://github.com/Dav1dde/glad) - Multi profile loader-generator based on the official specs.
* [glbindify](https://github.com/nnesse/glbindify) - Commmand line tool to generate C bindings for OpenGL, wgl, and glX.
* [glbinding](https://github.com/cginternals/glbinding) - Profile loader leveraging C++11 features to provide type safety.
* [GLEW](http://glew.sourceforge.net) - Mature cross-platform library to load OpenGL extensions.
* [glLoadGen](https://bitbucket.org/alfonse/glloadgen/wiki/Home) - Multi profile loader-generator written in Lua.

### **OpenGL Documentation**

For documentation and API information, the place to go to is the [official page on OpenGL](https://www.khronos.org/opengl/) by Khronos Group. It contains various useful links like [cheat sheets](https://www.khronos.org/files/opengl46-quick-reference-card.pdf), [wiki](https://www.khronos.org/opengl/wiki) etc.

<hr>

## **Shaders**

As I had explained in the [first section](#opengl) shader helps you control what happens in the arrows. By definition, a shader is a user-defined program designed to run on some stage of a graphics processor. Its purpose is to execute one of the programmable stages of the rendering pipeline. The word "Shader" comes from the word "Shading" which is a technique for producing appropriate levels of color, light etc in an image.

OpenGL shaders are written in [OpenGL Shading Langugage](https://www.khronos.org/opengl/wiki/OpenGL_Shading_Language). There are also other shading languages which are used by different tools like [CG](https://en.wikipedia.org/wiki/Cg_(programming_language)), [Metal](https://developer.apple.com/documentation/metal), DirectX etc. But, the difference is usually just a change in syntax. The general concepts of shader programming is the same across shaders. So, if you know how to program in say GLSL, it would be easy to convert it to a CG shader. 

In OpenGL shading language there are 5 types of shaders:

* Vertex Shaders: `GL_VERTEX_SHADER`
* Tessellation Control and Evaluation Shaders: `GL_TESS_CONTROL_SHADER` and `GL_TESS_EVALUATION_SHADER`. (requires GL 4.0 or ARB_tessellation_shader)
* Geometry Shaders: `GL_GEOMETRY_SHADER`
* Fragment Shaders: `GL_FRAGMENT_SHADER`
* Compute Shaders: `GL_COMPUTE_SHADER`. (requires GL 4.3 or ARB_compute_shader)

Compute Shaders are a bit different in the sense that they are programs that run on the graphics card outside of the normal rendering pipeline. They can be used for massively parallel GPGPU algorithms, or to accelerate parts of game rendering. Usually, for starters it is best to learn vertex and fragment shaders. 

There is a myth among programmers that shaders are painful to write. This is both true and false. Usually, what makes shaders painful is the fact shaders are difficult to debug and shader programming is different from conventional programming. It is creative and parallel, but once you get a hang of it, it can be a lot of fun and it is cool to see the actual effects of your program. What I mean is that, though it can be tedious, it can be really satisfying to see the final effects. For example:

<div>
<iframe onload="this.width=screen.width*0.3;this.height=screen.height*0.3;" frameborder="0" src="https://www.shadertoy.com/embed/Md3yRB?gui=true&t=10&paused=true&muted=false" allowfullscreen></iframe> 

<iframe onload="this.width=screen.width*0.3;this.height=screen.height*0.3;" frameborder="0" src="https://www.shadertoy.com/embed/4s3SRN?gui=true&t=10&paused=true&muted=false" allowfullscreen></iframe>
</div>

### **Learning Shader Programming**

#### **Books**

Like I had mentioned before, realtime rendering's [book page](http://www.realtimerendering.com/books.html) is really good and contains a nice collection of computer graphics related to books. So, if you are looking to learn a specific shader language, you should look up corresponding book on that page.

#### **Websites and Tutorials**

If you would like to learn fragment shaders, there are a lot of websites with tutorials on it like [The Book on Shaders](https://thebookofshaders.com/00/). The really cool part of a fragment shader is that, with just one quad (rectangle), you can do really cool stuff. 

* [Shadertoy](https://www.shadertoy.com/) is a WebGL based shader sharing platform. It has a really huge collection of fragment shaders. It was created by Pol Jeremias and Inigo Quilez from Pixar Animation Studios. The website makes it really easy to write shaders and link other stuff like keyboard inpur, sound, microphone input etc.

If you are new to shaders, I would **highly recommend** going through the following video by Pol Jeremias:

<center>
<iframe STYLE="width:48vw; height:27vw" src="https://www.youtube.com/embed/JIPOIi7QgYI" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</center>

I had attended a similar session at Siggraph Asia 2017. It is a really nice tutorial on fragment shaders and assumes that you have zero background knowledge.

* [Inigo Quilez's Website](http://www.iquilezles.org/www/index.htm): Inigo Quilez's website has some really nice experiments, tutorials, code on doing different effects using shaders.

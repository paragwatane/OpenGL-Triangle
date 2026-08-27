# 🔺 OpenGL Triangle

A simple **OpenGL 3.3 Core** project that renders a colorful 3D-positioned triangle using **GLFW, GLAD, and GLSL shaders**.

This project is based on the fundamentals of the OpenGL rendering pipeline — creating a window, sending vertex data to the GPU, compiling shaders, and drawing geometry.

## 🛠️ Technologies Used

* **C++**
* **OpenGL 3.3 Core**
* **GLFW** — Window and input management
* **GLAD** — OpenGL function loader
* **GLSL** — Vertex and Fragment shaders

## 📌 Features

* Creates an `800 × 600` OpenGL window
* Uses an OpenGL 3.3 Core context
* Initializes OpenGL through GLAD
* Creates and compiles:

  * Vertex Shader
  * Fragment Shader
* Uses a **VAO** and **VBO** to store and describe vertex data
* Renders a triangle using `glDrawArrays()`
* Uses a custom background and fragment shader color

## 🔄 How It Works

The program follows a basic OpenGL rendering pipeline:

```text
C++ Program
    ↓
Initialize GLFW
    ↓
Create OpenGL Window
    ↓
Initialize GLAD
    ↓
Compile Vertex Shader
    ↓
Compile Fragment Shader
    ↓
Link Shader Program
    ↓
Create VAO + VBO
    ↓
Upload Vertex Data to GPU
    ↓
Configure Vertex Attributes
    ↓
Render Triangle
    ↓
Swap Buffers + Handle Events
```

## 🔺 Vertex Data

The triangle is defined using three vertices:

```cpp
float vertices[] = {
    -0.5f, -0.5f, 0.0f,
     0.5f, -0.5f, 0.2f,
     0.0f,  0.9f, 0.0f
};
```

Each vertex contains three values:

```text
X    Y    Z
```

The `Z` value demonstrates that the vertex data contains a 3D position, even though the triangle is rendered directly in clip space.

## 🎨 Shaders

### Vertex Shader

The vertex shader receives the position through attribute location `0`:

```glsl
layout (location = 0) in vec3 aPos;
```

It then converts the position into a 4D homogeneous coordinate:

```glsl
gl_Position = vec4(aPos.x, aPos.y, aPos.z, 1.0);
```

### Fragment Shader

The fragment shader determines the triangle's color:

```glsl
FragColor = vec4(4.0f, 0.2f, 0.8f, 6.0f);
```

OpenGL ultimately clamps the resulting color components to the valid output range.

## 🧠 OpenGL Concepts Practiced

This project is a starting point for understanding:

* OpenGL Contexts
* GLFW Window Creation
* GLAD Initialization
* Vertex Buffers
* Vertex Array Objects
* Vertex Attributes
* Shader Compilation
* Shader Programs
* GLSL
* Rendering Loops
* Double Buffering
* `glDrawArrays()`

## 🚀 Getting Started

### Prerequisites

Make sure you have:

* A C++ compiler
* GLFW
* GLAD
* OpenGL 3.3 compatible graphics hardware/drivers

### Build & Run

Configure your project so that GLFW and GLAD are linked correctly, then compile the source file with your preferred C++ compiler.

Run the resulting executable and you should see an **800 × 600 window containing the triangle**.

## 📂 Project Structure

```text
OpenGL-Triangle/
│
├── main.cpp
├── glad/
├── GLFW/
└── README.md
```

> The exact structure may vary depending on how GLFW and GLAD are installed in your development environment.

## 📚 What I Learned

This project helped me understand the basic flow of data from a C++ program to the GPU:

**Vertex Data → VBO → VAO → Vertex Shader → Rasterization → Fragment Shader → Screen**

It's a small project, but it forms the foundation for more advanced OpenGL concepts such as textures, transformations, lighting, 3D models, camera systems, and more.

## 🔮 Future Improvements

* Add shader compilation error checking
* Add shader files instead of embedding GLSL in C++
* Add transformations using matrices
* Add keyboard/mouse input
* Add textures
* Add a 3D camera
* Render multiple objects
* Implement basic lighting
* Load 3D models

---

### ⭐ First Step into OpenGL

> *One triangle at a time.*


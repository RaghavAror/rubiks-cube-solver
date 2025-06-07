# Rubik's Cube Solver

A C++ application designed to simulate and solve a Rubik's Cube using OpenGL for graphics rendering. This project allows users to interact with a virtual Rubik's Cube, apply various rotations, and visualize the solving process.

---


## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
- [Algorithms and Techniques](#algorithms-and-techniques)
- [Controls](#controls)
- [Contributing](#contributing)
- [License](#license)


---

## Project Overview

This project is a Rubik's Cube simulator that provides an interactive 3D environment for users to manipulate a virtual Rubik's Cube. The application is built using C++ and leverages the OpenGL library for rendering graphics and animations.

---

## Features

- Interactive 3D Rubik's Cube visualization.
- Real-time cube manipulation using keyboard and mouse inputs.
- Support for various cube sizes (up to 50x50x50).
- Smooth animations and transitions.
- Random rotation functionality.
- Layer selection and manipulation.

---

## Project Structure

The project is structured as follows:

- `main.cpp`: The main source file containing the core logic and rendering code.
- `eigen/`: Directory containing the Eigen library for linear algebra operations.
- `freeglut/`: Directory containing the FreeGLUT library for OpenGL utility toolkit functions.

---



## Usage
Upon running the application, you will see a 3D Rubik's Cube. Use the keyboard and mouse controls to interact with the cube as described in the Controls section.

### Algorithms and Techniques

1. **Graphics and Animations**
-**OpenGL**: Used for rendering 3D graphics. The cube is drawn using a series of quadrilaterals, and transformations are applied to simulate rotations.
-**Quaternions**: Used for smooth and accurate 3D rotations. The Quaterniond class from the Eigen library helps in achieving complex rotations without the issue of gimbal lock.
-**Matrix Transformations**: Used for translating and rotating the cube in 3D space. The getRotationMatrix function converts quaternions to rotation matrices for OpenGL.

2. **Solving Algorithm**
The solver uses a series of predefined moves to manipulate the cube. The algorithm involves:
-**Layer Selection**: Users can select different layers of the cube to apply rotations.
-**Rotation Application**: Rotations are applied to the selected layers using quaternions and rotation matrices.
-**State Management**: The state of the cube is managed using a 3D array to keep track of the positions and orientations of each smaller cube.

3. **Controls**
-**Keyboard Controls**
**Q**: Front layer clockwise rotation.
**W**: Back layer clockwise rotation.
**A**: Left layer clockwise rotation.
**S**: Right layer clockwise rotation.
**Z**: Top layer clockwise rotation.
**X**: Bottom layer clockwise rotation.
**J**: Apply random rotations to the cube.
**1-9**: Select the corresponding layer of the cube.
**+/-**: Increment/Decrement the selected layer.
**SHIFT**: Apply anti-clockwise rotations.

4. **Mouse Controls**
-**Drag Vertically**: Rotate the cube along the X-axis.
-**Drag Horizontally**: Rotate the cube along the Y-axis.
-**Scroll Up/Down**: Rotate the cube along the Z-axis.

---

## Setup and Installation

### Prerequisites

- A C++ compiler that supports C++11 or later.
- OpenGL and FreeGLUT libraries installed.
- Eigen library for matrix and vector operations.

### Compilation

To compile the project, use the following command:

```bash
g++ -I"path/to/eigen" -I"path/to/freeglut/include" -L"path/to/freeglut/lib" main.cpp -lfreeglut -lopengl32 -o main.exe
```

Replace "path/to/eigen", "path/to/freeglut/include", and "path/to/freeglut/lib" with the actual paths to the Eigen and FreeGLUT directories on your system

---

## Running the Application

After compiling, run the executable:
```bash 
./main.exe
```
---

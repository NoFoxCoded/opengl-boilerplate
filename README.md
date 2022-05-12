# OpenGL Boilerplate 
Minimal boilerplate for OpenGL using [GLFW](https://www.glfw.org/) and [GLAD](https://glad.dav1d.de/) written in C++.



## Getting Started
```shell
opengl-boilerplate/
├─ build/               # build folder with copiled files
├─ external/            # external dependencies
├─ include/             # header files
├─ src/                 # source code for project
```
### Prerequisites
This projects needs to be build with [CMake](https://cmake.org/). Follow the instructions on [their](https://cmake.org/) website to install it.

### Clone
I try to manage all external dependencies as tracked submodules in the folder `external/`. In order to compile the program, all submodules must be initialized.

```shell
git clone https://github.com/NoFoxCoded/opengl-boilerplate.git --recursive
```
Alternatively, one can just clone the repository and add initialize the submodule afterwards:
```shell
git clone https://github.com/NoFoxCoded/opengl-boilerplate.git
git submodule init
git submodule update
```

### Build
The build is done with CMake. I recommend building the project in a new folder called `build/`
```shell
mkdir build
cd build
cmake .. # Run the cmake command where CMakeLists.txt is located
```

> You can use the GUI if you're more familiar with it.

## Name Changes
If you want to use this boilerplate for your own project, be aware to change following things in `CMakeLists.txt`:

1. Change `project(opengl-boilerplate)` to `project(your-new-name)`
2. Change `add_executable(opengl-boilerplate` to `add_executable(your-new-name`

## Build With
* [GLFW](https://www.glfw.org/) - Windowing library
* [GLAD](https://glad.dav1d.de/) - OpenGL loading library

## License
This project is licensed unter the MIT License - see [LICENSE](LICENSE) file for further details.

# freeglut compiled from src using cmake and added to project

## Instructions

### Windows

```shell
cmake -B build -G "Visual Studio 17 2022"

cmake --build build

build/Debug/main
```

### Ubuntu

install the following packages to support opengl.

```shell
sudo apt install libgl1-mesa-dev libglu1-mesa-dev libx11-dev libxrandr-dev libxi-dev
```

For more info see freeglut docs.

[freeglut/README.cmake](https://github.com/FreeGLUTProject/freeglut/blob/master/README.cmake)

```shell
cmake -B build

cmake --build build

build/main
```

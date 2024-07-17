# Cpp-Project-Template-with-VCPKG-and-CMake

A C++ Project template for VS Code with VCPKG and CMake

Setting up a C++ project in Windows with Visual Studio Code often involves using these tools for different purposes:

1. **MinGW (Minimalist GNU for Windows)**: This provides a GCC-based compiler toolchain on Windows, allowing you to compile and build C++ code. It's necessary because Windows doesn't come with a native C++ compiler like Linux does with GCC.

   - Download MinGW: [MinGW](https://github.com/msys2/msys2-installer/releases/download/2024-01-13/msys2-x86_64-20240113.exe)

2. **vcpkg**: This is a package manager for C and C++ libraries. It simplifies the process of acquiring and building open-source libraries on Windows. Many C++ projects rely on various libraries, and vcpkg helps manage their dependencies.

   - Download vcpkg: [vcpkg](https://github.com/microsoft/vcpkg)

3. **CMake**: CMake is a cross-platform build system generator. It allows you to describe your build process in a platform-independent way and generates native build scripts (like Makefiles for Unix systems or Visual Studio projects for Windows).

   - Download CMake: [CMake](https://cmake.org/download/)

4. **Ninja**: Ninja is a fast build system that works alongside CMake to execute the build process. It's designed to be lightweight and efficient, making it a popular choice for larger projects or projects where build times need to be minimized.

   - Download Ninja: [Ninja](https://ninja-build.org/)

Each of these tools serves a specific purpose in the development workflow:

- **MinGW** provides the compiler and related tools to actually compile and build your C++ code.
- **vcpkg** manages libraries and their dependencies, ensuring that you can easily integrate third-party libraries into your project.
- **CMake** creates the build configuration files based on your project structure and dependencies, ensuring cross-platform compatibility.
- **Ninja** (or other build systems like Visual Studio's MSBuild or Make) executes the build commands efficiently based on the configuration provided by CMake.

While it may seem like a lot of tools, each one addresses a different aspect of the build and development process, ensuring that your C++ project can be developed, built, and run smoothly on a Windows platform.

## Installing a C++ compiler

A compiler is a tool that translates source code written in a programming language (like C++) into machine code.
To compile and run C++ code in VS Code, I followed the steps listed [Here](#). There are two ways to have the compiler installed: MSVC or MinGW.

I chose to install **MinGW** (Minimalist GNU for Windows) via **MSYS2** since it is not tightly bound to Microsoft. Below are the steps I took to install MinGW on Windows.

1. Download the installer [`msys2-x86_64-20240113.exe`](https://github.com/msys2/msys2-installer/releases/download/2024-01-13/msys2-x86_64-20240113.exe).
2. Run the installer. MSYS2 requires 64-bit Windows 8.1 or newer. Clicking finish will open the terminal.

3. Paste the following command in the terminal to install the toolchain:

```
pacman -S mingw-w64-x86_64-toolchain
```

4. Ensure `C:\msys64\mingw64\bin` and `C:\msys64\ucrt64\bin` are set in your environment variables.

5. Open cmd and type in :

```
gcc -version
g++ --version
gdb --version
```

## Package Manager for C++

vcpkg is a free and open-source C/C++ package manager maintained by Microsoft and the C++ community. I use the package manager to install the Indicators library to show progress bar while the files are downloading. To install the vcpkg I followed the tutorial on [here](https://learn.microsoft.com/en-us/vcpkg/get_started/overview).

Ensure the following environment variables are set: `VCPKG_ROOT` to `C:\Users\name\vcpkg`. To confirm type the below in CMD:

```
echo %VCPKG_ROOT%
```

## Setting up the build system

We will use **CMake**: A cross-platform build system generator that can produce build scripts for various native build systems like Make, Ninja, and Visual Studio.
Download and Install from [Here](https://cmake.org/download/).

## Setting up Ninja

Download and extract the Ninja file into :

```
C:\ninja
```

Add `C:\ninja` into environment variables path. Fire this command in power shell to see if the path was registered:

```
$Env:Path
```

## VS Code extensions

Open VS Code code and add the following extensions:

1. [CMake Tools extensions into your VS Code](https://marketplace.visualstudio.com/items?itemName=twxs.cmake)
2. [C/C++ ](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools)

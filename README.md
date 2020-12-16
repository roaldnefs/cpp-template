# C++ Template

C++ project template using CMake.

## Usage

## Adjust the template to your needs

- Use this repository [as a template](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template) and replace all occurrences of `Boilerplate` in the relevant `CMakeLists.txt` with the name of your project.
- Replace the source files with your own.
- See the comments in [CMakeLists.txt](CMakeLists.txt) for header-only libraries.

### Build and run the standalone target

Use the following command to build and run the executable target:

```console
$ cmake -Hstandalone -Bbuild/standalone
$ cmake --build build/standalone
$ ./build/standalone/Boilerplate --help
```

## Acknowledgements

This project is a derivative of the [CMake Tutorial](https://cmake.org/cmake-tutorial/) and [ModernCppStarter](https://github.com/TheLartians/ModernCppStarter) by [TheLartians](https://github.com/TheLartians), and is aimed at saving time for starting new projects in C++ that use CMake.

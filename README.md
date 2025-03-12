## C Example using OpenIAP installed using conan to connect to OpenCora
To build the project, you need to have [conan](https://conan.io/) installed.
```sh
rm -rf build
conan install . --build=missing --output-folder=build
cmake --preset conan-release -DCMAKE_EXPORT_COMPILE_COMMANDS=ON
cmake --build build
./build/test_openiap
```

To debug
```sh
rm -rf build
conan install . --build=missing --output-folder=build -s build_type=Debug
cmake --preset conan-debug -DCMAKE_EXPORT_COMPILE_COMMANDS=ON
cmake --build build
./build/test_openiap
```
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

To use in your project, first install it
```sh
conan install --require=openiap/0.0.1 --output-folder=build
```

Then, in your CMakeLists.txt
```cmake
find_package(openiap REQUIRED)
target_link_libraries(your_target PRIVATE openiap::openiap)
```

Clearing conan cache
```
conan remove "*" -c
```
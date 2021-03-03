cmake_minimum_required(VERSION 3.10)
project(emscripten_cmake)

# If you want to write the path of the sdk to CMake, please uncomment the content below. Otherwise you need
# use -DCMAKE_TOOLCHAIN_FILE

# set(CMAKE_TOOLCHAIN_FILE "path/to/Emscripten.cmake")

set(CMAKE_CXX_STANDARD 14)

set(flag "\
        -s SAFE_HEAP=1 \
        -s WASM=1
        ")

add_executable(emscripten_cmake src/main.cpp)
set_target_properties(emscripten_cmake PROPERTIES LINK_FLAGS ${flag} DEBUG_POSTFIX "d")
cmake_minimum_required(VERSION 3.22)
project(flarial_gui LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

# NDK 30 / Clang 21: fmt (from the SDK) needs <cstdlib> for malloc/free
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -include cstdlib")

include(FetchContent)
FetchContent_Declare(
    preloader_android
    GIT_REPOSITORY https://github.com/LiteLDev/preloader-android.git
    GIT_TAG 0.2.2)
FetchContent_MakeAvailable(preloader_android)

# Full mod
add_library(flarial_gui SHARED src/main.cpp)
target_include_directories(flarial_gui PRIVATE src)
target_link_libraries(flarial_gui PRIVATE preloader log)

# Minimal twin: same file, but enable() does nothing
add_library(flarial_min SHARED src/main.cpp)
target_compile_definitions(flarial_min PRIVATE FG_MINIMAL=1)
target_include_directories(flarial_min PRIVATE src)
target_link_libraries(flarial_min PRIVATE preloader log)

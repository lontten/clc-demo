cmake_minimum_required(VERSION 3.30)
project(clc_demo)

set(CMAKE_CXX_STANDARD 20)

include(FetchContent)

FetchContent_Declare(
        clc
        GIT_REPOSITORY https://gitee.com/lontten/clc.git
        GIT_TAG main
)
FetchContent_MakeAvailable(clc)


add_executable(clc_demo main.cpp)

target_include_directories(clc_demo PRIVATE ${clc_SOURCE_DIR}/include)
target_link_libraries(clc_demo PRIVATE clc)
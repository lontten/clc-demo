cmake_minimum_required(VERSION 3.30)
project(clc_demo)

set(CMAKE_CXX_STANDARD 20)

include(FetchContent)

FetchContent_Declare(
        clc
        GIT_REPOSITORY https://github.com/lontten/clc.git
        #GIT_REPOSITORY https://gitee.com/lontten/clc.git # 国内可以使用gitee
        GIT_TAG main
)
set(CLC_BUILD_EXAMPLES OFF CACHE BOOL "Disable clc examples") # 关闭示例项目
FetchContent_MakeAvailable(clc)


add_executable(clc_demo main.cpp)
target_link_libraries(clc_demo PRIVATE clc)
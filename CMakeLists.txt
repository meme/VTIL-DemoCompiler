cmake_minimum_required(VERSION 3.15)

project(VTIL-DemoCompiler)

include(FetchContent)

set(ASMJIT_STATIC TRUE)

FetchContent_Declare(
    asmjit
    GIT_REPOSITORY https://github.com/asmjit/asmjit.git
    GIT_SHALLOW    true
)

FetchContent_Declare(
    VTIL-Core
    GIT_REPOSITORY https://github.com/vtil-project/VTIL-Core
    GIT_SHALLOW    true
)
FetchContent_MakeAvailable(VTIL-Core asmjit)

add_executable(${PROJECT_NAME} VTIL-DemoCompiler.cpp)

target_link_libraries(${PROJECT_NAME} PRIVATE VTIL asmjit)

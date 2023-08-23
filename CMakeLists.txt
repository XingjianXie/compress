cmake_minimum_required(VERSION 3.5)

project(MyProject)

# Create a library
add_library(MyLibrary STATIC
    src/lib.c
)

target_include_directories(MyLibrary PUBLIC
    include
)

# Create an executable
add_executable(MyExecutable
    src/main.c
)

target_link_libraries(MyExecutable PRIVATE
    MyLibrary
)

add_subdirectory(zfp)
target_link_libraries(MyLibrary PUBLIC zfp::zfp)
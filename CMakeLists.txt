cmake_minimum_required(VERSION 3.10)

project(opengl_project)

# set release
set(CMAKE_BUILD_TYPE Release)

# add freeglut library as subdirectory
add_subdirectory(freeglut)

# add the library include directory
include_directories(freeglut/include)

# Add the executable target
add_executable(main main.cpp)

# Copy the freeglutd.dll file to the executable dir
if(WIN32)
    add_custom_command(TARGET main POST_BUILD COMMAND ${CMAKE_COMMAND} -E copy_if_different "${CMAKE_BINARY_DIR}/freeglut/bin/Debug/freeglutd.dll" "${CMAKE_BINARY_DIR}/Debug")
endif()

if(WIN32)
    # Link against the freeglut library and opengl (WIN32)
    target_link_libraries(main PRIVATE freeglut opengl32)
elseif(UNIX)
    # Link against the freeglut library and opengl (UNIX)
    target_link_libraries(main PRIVATE freeglut GL)
endif()

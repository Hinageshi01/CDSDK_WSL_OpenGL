cmake_minimum_required (VERSION 3.8)

project ("WSL_OpenGL")

include_directories(include include/CDScene source)
link_directories(lib)

add_executable(WSL_OpenGL
    source/glad.c
    source/camera.cpp
    source/shader.cpp
    source/mesh.cpp
    source/GLConsumer.cpp
    source/model.cpp
    source/WSL_OpenGL.cpp)

target_link_libraries(WSL_OpenGL
        -lglfw
        -lGL
        -lm
        -lXrandr
        -lXi
        -lX11
        -lXxf86vm
        -lpthread
        -ldl
        -lXinerama
        -lXcursor
        -lAssetPipelineCore
        -lCDProducer
        )

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET WSL_OpenGL PROPERTY CXX_STANDARD 20)
endif()
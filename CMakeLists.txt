project(imgui)

file(GLOB SOURCES
    "*.cpp"
    "*.h"
    "examples/imgui_impl_glfw.cpp"
    "examples/imgui_impl_glfw.h"
    "examples/imgui_impl_opengl3.cpp"
    "examples/imgui_impl_opengl3.h"
)
source_group("Source Files" FILES ${SOURCES})

## Specify target rules
add_library(${PROJECT_NAME} STATIC ${SOURCES})
target_link_libraries(${PROJECT_NAME}
    ${GLEW_LIBRARIES}
    ${OPENGL_LIBRARIES}
    glfw3
)

add_definitions(-DIMGUI_INCLUDE_IMCONFIG_H -DIMGUI_EXPORTS)

target_include_directories(${PROJECT_NAME} PUBLIC . "examples")


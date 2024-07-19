file(GLOB_RECURSE imgui_hdrs "*.h")
file(GLOB_RECURSE imgui_src "*.cpp")

add_library(imgui 
    "${imgui_hdrs};${imgui_src}")

if(WIN32)
    target_link_libraries(imgui PUBLIC "glfw;opengl32")
elseif(linux)
    target_link_libraries(imgui PUBLIC "glfw;GL")
endif()

target_include_directories(imgui PUBLIC ".")
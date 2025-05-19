file(
  GLOB_RECURSE
  SOURCES
  CONFIGURE_DEPENDS
  "src/*.cpp"
  "src/*.hpp"
  "src/*.h"
  "include/*.hpp"
  "include/*.h"
)

add_library(imgui-backend-sdl3 STATIC ${SOURCES})
add_library(imgui::imgui-sdl3 ALIAS imgui-backend-sdl3)

target_include_directories(imgui-backend-sdl3 SYSTEM PUBLIC "include")

target_link_libraries(imgui-backend-sdl3 PRIVATE imgui)

find_package(SDL3 REQUIRED CONFIG)
target_link_libraries(imgui-backend-sdl3 PRIVATE SDL3::SDL3)

set_target_properties(imgui-backend-sdl3
  PROPERTIES
    CXX_STANDARD 23
    CXX_STANDARD_REQUIRED YES
    CXX_EXTENSIONS NO
)

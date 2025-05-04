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

add_library(imgui STATIC ${SOURCES})

target_include_directories(imgui SYSTEM PUBLIC "include")

set_target_properties(imgui
  PROPERTIES
    CXX_STANDARD 23
    CXX_STANDARD_REQUIRED YES
    CXX_EXTENSIONS NO
)

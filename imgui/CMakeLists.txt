project(imgui)

file(GLOB SOURCE_FILES
  "src/*.cpp"
)

add_library(imgui STATIC ${SOURCE_FILES})

target_include_directories(imgui SYSTEM PUBLIC "include")

set_target_properties(imgui
  PROPERTIES
    CXX_STANDARD 20
    CXX_STANDARD_REQUIRED YES
    CXX_EXTENSIONS NO
)

project(imgui-backend-sdl3)

file(GLOB SOURCE_FILES
  "src/*.cpp"
)

add_library(imgui-backend-sdl3 STATIC ${SOURCE_FILES})

target_include_directories(imgui-backend-sdl3 SYSTEM PUBLIC "include")

target_link_libraries(imgui-backend-sdl3 PRIVATE imgui)

find_package(SDL3 REQUIRED CONFIG REQUIRED COMPONENTS SDL3-shared)
target_link_libraries(imgui-backend-sdl3 PRIVATE SDL3::SDL3)

# find_package(glfw3 REQUIRED)
# target_link_libraries(imgui-backend-sdl3 PRIVATE glfw)

# target_link_libraries(imgui-backend-sdl3 PRIVATE glad)

#find_package(OpenGL REQUIRED)
#target_link_libraries(gameboy-emulator-glfw PRIVATE OpenGL::GL)

set_target_properties(imgui-backend-sdl3
  PROPERTIES
    CXX_STANDARD 23
    CXX_STANDARD_REQUIRED YES
    CXX_EXTENSIONS NO
)
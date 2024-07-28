project(imgui-backend-sdl2)

file(GLOB SOURCE_FILES
  "src/*.cpp"
)

add_library(imgui-backend-sdl2 STATIC ${SOURCE_FILES})

target_include_directories(imgui-backend-sdl2 SYSTEM PUBLIC "include")

target_link_libraries(imgui-backend-sdl2 PRIVATE imgui)

find_package(SDL2 2.0 REQUIRED)
target_link_libraries(imgui-backend-sdl2 PRIVATE SDL2::SDL2)

# find_package(glfw3 REQUIRED)
# target_link_libraries(imgui-backend-sdl2 PRIVATE glfw)

# target_link_libraries(imgui-backend-sdl2 PRIVATE glad)

#find_package(OpenGL REQUIRED)
#target_link_libraries(gameboy-emulator-glfw PRIVATE OpenGL::GL)

set_target_properties(imgui-backend-sdl2
  PROPERTIES
    CXX_STANDARD 23
    CXX_STANDARD_REQUIRED YES
    CXX_EXTENSIONS NO
)
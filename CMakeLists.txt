cmake_minimum_required(VERSION 4.2.3)
project(learnogl)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_subdirectory(include)

add_subdirectory(src)

if(UNIX AND NOT APPLE)

  target_compile_options(${PROJECT_NAME}
    PRIVATE
      -lglfw
      -lGL
      -lX11
      -lpthread
      -lm
      -ldl

      -Wall
      -Werror
      -std=c++20
  )

elseif(WIN32)

  target_compile_options(${PROJECT_NAME}
  # Bsage! You may need to edit these flags for this to build successfully
  # I don't know exactly which flags you need to compile for windows

    #libraries to link against
    -lglfw3
    -lopengl32
    -lgdi32

    # Wall and Werror to treat warnings as Werror
    # standard set to C++ 2020, you can change this if you like (eg -std=c++17)
    -Wall
    -Werror
    -std=c++20
  )

endif()

cmake_minimum_required(VERSION 3.25)
project(2D_game_assignment)

set(CMAKE_CXX_STANDARD 14)

# Set the path to the SFML CMake modules
set(SFML_DIR "/opt/homebrew/Cellar/sfml/2.6.1/lib/cmake/SFML")

# Find SFML
find_package(SFML 2.6 COMPONENTS graphics window system REQUIRED)

include_directories(include)

configure_file(resources/background.png ${CMAKE_CURRENT_BINARY_DIR}/resources/background.png COPYONLY)
configure_file(resources/pacman.png ${CMAKE_CURRENT_BINARY_DIR}/resources/pacman.png COPYONLY)

add_executable(2D_game_assignment
        src/main.cpp
        src/game.cpp
        src/game.cpp)

# Link SFML Libraries
target_link_libraries(2D_game_assignment sfml-graphics sfml-window sfml-system)

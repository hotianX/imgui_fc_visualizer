cmake_minimum_required(VERSION 4.0)
project(imgui_fc_visualizer)

set(CMAKE_CXX_STANDARD 20)

add_subdirectory(3rd_party)

# Main application with audio visualizer
add_executable(imgui_fc_visualizer
    main.cpp 
    AudioVisualizer.cpp 
    AudioVisualizer.h
)
target_link_libraries(imgui_fc_visualizer PRIVATE sokol imgui game_music_emu nfd)

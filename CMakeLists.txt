cmake_minimum_required(VERSION 4.0)
project(imgui_fc_visualizer)

set(CMAKE_CXX_STANDARD 20)

add_subdirectory(3rd_party)

# Main application with audio visualizer and NES emulator
add_executable(imgui_fc_visualizer
    main.cpp
    impl.cpp
    AudioVisualizer.cpp 
    AudioVisualizer.h
    PianoVisualizer.cpp
    PianoVisualizer.h
    NesEmulator.cpp
    NesEmulator.h
)
target_link_libraries(imgui_fc_visualizer PRIVATE sokol imgui game_music_emu agnes nfd)

# Include directories for gme headers
target_include_directories(imgui_fc_visualizer PRIVATE 
    ${CMAKE_SOURCE_DIR}/3rd_party/Game_Music_Emu
    ${CMAKE_SOURCE_DIR}/3rd_party
)

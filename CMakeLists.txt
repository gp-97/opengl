cmake_minimum_required(VERSION 3.14.0)

project(lopgl)

add_executable(${PROJECT_NAME}
    # src/SettingUpWindow/main.cpp
    src/TriangleCreation/main.cpp
)

add_subdirectory(libs/glad)
add_subdirectory(libs/glfw)

target_include_directories(${PROJECT_NAME}
    PUBLIC libs/glfw/include/
    PUBLIC libs/glad
)

target_link_directories(${PROJECT_NAME} 
    PUBLIC libs/glfw/src
    PRIVATE libs/glad/src
)

target_link_libraries(${PROJECT_NAME}
    glad
    glfw
)


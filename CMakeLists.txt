cmake_minimum_required(VERSION 2.8.12)

set(PROJECT Testprojekt)
project(${PROJECT})

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11") 
#SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g") #debug

# disable policy warning
if(POLICY CMP0020)
  cmake_policy(SET CMP0020 NEW)
endif()

set (CMAKE_C_FLAGS "-m32")

# Find includes in corresponding build directories
set(CMAKE_INCLUDE_CURRENT_DIR ON)
# Instruct CMake to run moc automatically when needed.
set(CMAKE_AUTOMOC ON)

# Find the QtWidgets library
find_package(Qt5Widgets)

file(GLOB UI_FILES ui/*.ui)
qt5_wrap_ui(UI_HEADERS ${UI_FILES})

file(GLOB CPP src/*.cpp)
file(GLOB H include/*.h)
file(GLOB GENERATED include/generated/*)
file(GLOB UI ui/*.ui)
include_directories(include)
include_directories(include/generated)

add_executable(${PROJECT} ${CPP} ${H} ${GENERATED} ${UI_HEADERS})

target_link_libraries(${PROJECT} Qt5::Widgets)
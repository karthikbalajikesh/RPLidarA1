cmake_minimum_required(VERSION 3.5.1)

#################### Project Name ###################3
project(RPlidar)

###############  Compiler Properties  #######################
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)
set(CMAKE_BUILD_TYPE "Release")

##############   Threads Library required ##############33
find_package(Threads REQUIRED)
set(LIBS ${CMAKE_THREAD_LIBS_INIT})

############## Include Directories ######################
include_directories(include)
FILE(GLOB SOURCES "src/*")

############# Library Location ########################
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "../lib")

############ Add Library #############################
add_library(rplidar SHARED ${SOURCES})
target_link_libraries(rplidar ${LIBS})

cmake_minimum_required(VERSION 3.10)
project(20S-3353-PA02)
set (EXE_NAME LinkSearchingAndCommunityDiscovery)

##########################################
# Students, edit the items below.  In the quotes,
# put the names of the input files as they should appear
# in the argv param to main.
# Example:
#   set (input01 "train_data.csv")
#   set (input02 "train_target.csv")
# etc....

set (input01 "controlFile.txt")
set (input02 "g1.txt")
set (input03 "pa03-karate-with-dashes.txt")
set (input04 "pa03-football-with-dashes.txt")
set (input03 "g2.txt")
#
##########################################

# Copy data files to build dir
foreach(file IN LISTS input01 input02 input03 input04)
    configure_file(${file} ${file} COPYONLY)
endforeach()

set(CMAKE_CXX_STANDARD 14)
set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${GCC_COVERAGE_COMPILE_FLAGS}-Wall -Wextra")
add_executable(${EXE_NAME} main.cpp)
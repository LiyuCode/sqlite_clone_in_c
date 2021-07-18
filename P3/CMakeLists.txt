cmake_minimum_required(VERSION 3.10) 

# fixing: initializer element is not constant
SET(CMAKE_C_COMPILER /usr/bin/clang)

# set the project name 
project(SQLITE_CLONE)

# add the executable 
add_executable(db.out db.c)
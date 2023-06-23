cmake_minimum_required(VERSION 3.0)
project(MingwTest)

if (MINGW)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -static")
endif()


add_executable(main
    main.cpp
)

cmake_minimum_required(VERSION 3.0)
project(MingwTest)

if (MINGW)
    set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -static-libgcc -static-libstdc++ -static-libwinpthread")
endif()


add_executable(main
    main.cpp
)
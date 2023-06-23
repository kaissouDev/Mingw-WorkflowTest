cmake_minimum_required(VERSION 3.0)
project(MingwTest)

if (MINGW)
    set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -static-libstdc++ -static-libgcc -Wl,--enable-auto-image-base -Wl,--add-stdcall-alias -Wl,--enable-auto-import")
    set(CMAKE_SHARED_LINKER_FLAGS "${CMAKE_SHARED_LINKER_FLAGS} -static-libstdc++ -static-libgcc")
    
    find_library(LIBWINPTHREAD_LIBRARY NAMES libwinpthread.a)
    target_link_libraries(mon_executable PRIVATE ${LIBWINPTHREAD_LIBRARY})
endif()


add_executable(main
    main.cpp
)
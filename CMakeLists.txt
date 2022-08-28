cmake_minimum_required(VERSION 3.10)

project(shellcodetest)
set(CMAKE_C_COMPILER /usr/bin/x86_64-w64-mingw32-gcc)
set(CMAKE_CXX_COMPILER /usr/bin/x86_64-w64-mingw32-g++)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O2 -mwindows -static-libgcc -static-libstdc++ -w")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS}")
set(CMAKE_CXX_STANDARD 17)

file(GLOB_RECURSE sourcefiles
    "*.h"
    "*.cc"
)

add_executable(shellcodetest.exe ${sourcefiles})
target_link_libraries(shellcodetest.exe d3d9 dwmapi ntdll winmm ws2_32 stdc++fs version)
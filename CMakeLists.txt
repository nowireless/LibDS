cmake_minimum_required(VERSION 3.5)   # CMake version check
project(simple_example)               # Create project "simple_example"
set(CMAKE_CXX_STANDARD 11)            # Enable c++11 standard

include_directories(include lib/Socky/include)

set(SOURCE_FILES
        src/array.c src/client.c src/config.c src/crc32.c
        src/events.c src/init.c src/joysticks.c src/protocols.c
        src/queue.c src/socket.c src/string.c src/timer.c src/utils.c
        src/protocols/frc_2014.c src/protocols/frc_2015.c src/protocols/frc_2016.c
        lib/Socky/src/socky.c)

add_library(DS ${SOURCE_FILES})

install(TARGETS DS DESTINATION lib)
install(FILES include/DS_Array.h include/DS_Client.h include/DS_Config.h include/DS_DefaultProtocols.h
        include/DS_Events.h include/DS_Joysticks.h include/DS_Protocol.h include/DS_Queue.h include/DS_Socket.h
        include/DS_String.h include/DS_Timer.h include/DS_Types.h include/DS_Utils.h include/LibDS.h
        DESTINATION include)
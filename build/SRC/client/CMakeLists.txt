cmake_minimum_required (VERSION 2.6)

find_package(Qt5Widgets)

set(CMAKE_AUTOMOC ON)
set(CMAKE_INCLUDE_CURRENT_DIR ON)

include_directories(../led)
include_directories(../commandhandler)
include_directories(../../bin)

set (PROJECT 
	client
)

set (HEADERS
	client.h 
	connectionthread.h
	netsettingsdlg.h
)

set (SOURCES 
	client.cpp
	connectionthread.cpp
	netsettingsdlg.cpp
	main.cpp
)

source_group ("Headers Files" FILES ${HEADERS})
source_group ("Sources Files" FILES ${SOURCES})

add_executable(${PROJECT} ${HEADERS} ${SOURCES})
qt5_use_modules(${PROJECT} Core Gui Widgets Network)
target_link_libraries(${PROJECT} led commandhandler)


cmake_minimum_required(VERSION 2.8)
project(ADVDIFF)
set(SOURCE main.cpp stencil.cpp checks.cpp limited_average.cpp save_mesh.cpp conv_diff.cpp)
set(HEADER stencil.h checks.h limited_average.h save_mesh.h conv_diff.h)


find_package(inmost REQUIRED)

link_directories(${INMOST_LIBRARY_DIRS})
include_directories(${INMOST_INCLUDE_DIRS})
add_definitions(${INMOST_DEFINITIONS})

add_executable(ADVDIFF ${SOURCE} ${HEADER})

target_link_libraries(ADVDIFF ${INMOST_LIBRARIES})

install(TARGETS ADVDIFF EXPORT inmost-targets RUNTIME DESTINATION bin)

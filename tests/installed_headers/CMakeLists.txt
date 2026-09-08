cmake_minimum_required(VERSION 3.1)
project(qtermwidget_installed_headers_smoke LANGUAGES CXX)

# This project deliberately consumes only the installed public package.  Run
# it after `cmake --install` with CMAKE_PREFIX_PATH containing both the
# qtermwidget install prefix and the Qt kit used to build that prefix.
find_package(Qt5 5.7 REQUIRED COMPONENTS Widgets)
find_package(qtermwidget5 CONFIG REQUIRED)

add_executable(qtermwidget_installed_headers_smoke main.cpp)
target_link_libraries(qtermwidget_installed_headers_smoke PRIVATE qtermwidget5)

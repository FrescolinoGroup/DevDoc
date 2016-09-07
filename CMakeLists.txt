# general settings
cmake_minimum_required (VERSION 3.0)
project(DevDoc
        VERSION 0.0)

enable_testing()

set(FSC_WEBSITE ${PROJECT_SOURCE_DIR}/../../website/frescolino)

# if additional cmake modules are needed
list(APPEND CMAKE_MODULE_PATH 
    /usr/include /usr/local/include
    ~/.local/include ${PROJECT_SOURCE_DIR}/../cmake_extensions)

include(fsc/softinstall)
include(fsc/uninstall)

# add subdirs
add_subdirectory(${PROJECT_SOURCE_DIR}/doc)

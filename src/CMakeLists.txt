# Optionally glob, but only for CMake 3.12 or later:
#file(GLOB HEADER_LIST CONFIGURE_DEPENDS "${RnnNoise_SOURCE_DIR}/include/rnnoise/*.h")
file(GLOB SRC_LIST CONFIGURE_DEPENDS "*.c")

# Make an automatic library - will be static or dynamic based on user setting
add_library(rnnoise_target ${SRC_LIST})

# We need this directory, and users of our library will need it too
target_include_directories(rnnoise_target 
    PUBLIC 
        $<INSTALL_INTERFACE:include>    
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../include>
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}/../include/rnnoise
)

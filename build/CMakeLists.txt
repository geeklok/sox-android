cmake_minimum_required(VERSION 3.4.1)

subdirs(../sox)

include_directories(..)

file(GLOB sources
    "../bionic/*.cpp"
    "../stdio/*.c"
    "../stdioext/*.c"
    "../stdlib/*.c"
)

include_directories(..)

add_library( sox-android

             STATIC

             ${sources} )

target_link_libraries( sox-android libsox gsm lpc10 )
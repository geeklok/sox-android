cmake_minimum_required(VERSION 3.4.1)

file(GLOB sources
    "../bionic/*.cpp"
    "../stdio/*.c"
    "../stdioext/*.c"
    "../stdlib/*.c"
)

add_library( sox-android

             STATIC

             ${sources} )

include_directories(..)

target_link_libraries( sox-android libsox gsm lpc10 )

subdirs(../sox)
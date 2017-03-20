cmake_minimum_required(VERSION 3.4.1)

# build sox's libraries first
subdirs(../sox)

# build android related library
include_directories(..)
include_directories(../private)

file(GLOB sources
    "../bionic/*.cpp"
    "../stdio/*.c"
    "../stdioext/*.c"
    "../stdlib/*.c"
)

add_library( sox-android

             STATIC

             ${sources} )

target_link_libraries( sox-android libsox gsm lpc10 )
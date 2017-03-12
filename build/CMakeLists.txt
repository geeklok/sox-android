cmake_minimum_required(VERSION 3.4.1)

subdirs(../sox)

file(GLOB sources
    "../bionic/*.cpp"
    "../stdio/*.c"
    "../stdioext/*.c"
    "../stdlib/*.c"
)

include_directories(..)

add_library( android

             STATIC

             ${sources} )

add_custom_target( sox-android ALL
  COMMAND ${CMAKE_AR} rc libs/${CMAKE_ANDROID_ARCH_ABI}/libsox-android.a $<TARGET_FILE:android> $<TARGET_FILE:libsox> $<TARGET_FILE:lpc10> $<TARGET_FILE:gsm> )
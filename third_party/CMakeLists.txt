include(${CMAKE_CURRENT_LIST_DIR}/cmake-build-sys-utilities/scripts/os_host_opts.cmake)
set(MAKE_ALTERNATIVES "")
if(${CMAKE_HOST_SYSTEM_NAME} STREQUAL "Windows")

elseif(${CMAKE_HOST_SYSTEM_NAME} STREQUAL "Darwin")
    set(MAKE_ALTERNATIVES "make")
elseif( ${CMAKE_HOST_SYSTEM_NAME} STREQUAL "Linux")
    set(MAKE_ALTERNATIVES "make")
else()
    message(FATAL_ERROR "\"${CMAKE_HOST_SYSTEM_NAME}\" is not a supported build host OS.")
endif()

look_for_dependency_program(${MAKE_ALTERNATIVES})
message(STATUS ${PROGRAM_FOUND})

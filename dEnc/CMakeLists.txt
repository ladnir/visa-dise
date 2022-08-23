

file(GLOB_RECURSE SRCS ${CMAKE_CURRENT_SOURCE_DIR}/*.cpp)
 

add_library(dEnc ${SRCS})
target_link_libraries(dEnc oc::cryptoTools)
target_include_directories(dEnc PUBLIC "${CMAKE_CURRENT_LIST_DIR}/..")


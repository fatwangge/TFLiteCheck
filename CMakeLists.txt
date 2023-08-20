cmake_minimum_required(VERSION 3.17)
project(TFLiteCheck)
set(CMAKE_CXX_STANDARD 17)

# include has 2 subdirectories: tensorflow and flatbuffers
#INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/tfliteDist/include/)
INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/tfliteDist/include/)

# lib has 3 file: tensorflowlite.dll.if.lib flatbuffers.lib tensorflowlite.dll
#find_library(TFLITE tensorflowlite.dll.if HINTS ${CMAKE_CURRENT_SOURCE_DIR}/tfliteDist/libs/)
#find_library(FLATBUFFERS flatbuffers  HINTS ${CMAKE_CURRENT_SOURCE_DIR}/tfliteDist/libs/)

#link_directories(${CMAKE_CURRENT_SOURCE_DIR}/tfliteDist/libs/)
link_directories(${PROJECT_SOURCE_DIR}/tfliteDist/libs/)
#link_directories(E:/GitHubRepository/TFLiteCheck/tfliteDist/libs)
link_libraries(tensorflowlite.dll.if flatbuffers)

#set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)

add_executable(TFLiteCheck main.cpp)
#target_link_libraries(TFLiteCheck PRIVATE ${TFLITE} ${FLATBUFFERS})

add_custom_command(
    TARGET ${PROJECT_NAME} POST_BUILD
    COMMAND ${CMAKE_COMMAND} -E copy ${PROJECT_SOURCE_DIR}/tfliteDist/libs/tensorflowlite.dll ${CMAKE_BINARY_DIR}/Release/
)
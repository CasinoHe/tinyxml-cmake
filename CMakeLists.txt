cmake_minimum_required(VERSION 3.16.0)

project(tinyxml)

set(TINYXML_ROOT ${CMAKE_CURRENT_SOURCE_DIR})

set(SRC_FILES
  ${TINYXML_ROOT}/tinyxml.cpp
  ${TINYXML_ROOT}/tinyxmlparser.cpp
  ${TINYXML_ROOT}/xmltest.cpp
  ${TINYXML_ROOT}/tinyxmlerror.cpp
  ${TINYXML_ROOT}/tinystr.cpp
)

if (TINYXML_USE_STL)
  target_compile_definitions(${PROJECT_NAME} PRIVATE -DTIXML_USE_STL)
endif()

add_library(${PROJECT_NAME} SHARED ${SRC_FILES})
add_library(${PROJECT_NAME}Static STATIC ${SRC_FILES})
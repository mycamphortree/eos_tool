include_directories(${PROJECT_SOURCE_DIR})
include_directories(${PROJECT_SOURCE_DIR}/src)
link_directories( /usr/local/boost_1_66_0/stage/lib ${PROJECT_BINARY_DIR}/lib)

ADD_DEFINITIONS(-DBOOST_ALL_DYN_LINK)
set(MAIN_SRC_LIST
 mystr.cpp
 readcfg.cpp
 testmain.cpp
  )

set(MAIN_HEADERS
  mystr.h 
  readcfg.h
  testmain.h
)

#file(GLOB HEADERS "*.h")
#add_library(ethcore ${SRC_LIST} ${HEADERS})
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
#add_executable(testma ${APP_SRC})

set(IMPORTLIB 
pthread  boost_system boost_filesystem boost_program_options boost_thread boost_thread   m
boost_log_setup  boost_log

)

add_executable(testboost ${MAIN_SRC_LIST}  ${MAIN_HEADERS})
target_link_libraries(testboost ${IMPORTLIB})



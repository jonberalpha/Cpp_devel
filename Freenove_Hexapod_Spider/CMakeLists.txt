cmake_minimum_required(VERSION 3.16)

project(Spider VERSION 0.1.0)

add_subdirectory(BCM2835)
add_subdirectory(smbus)

add_subdirectory(RaspiLib)
add_subdirectory(RaspiBlocks)
add_subdirectory(Spider)

add_subdirectory(SpiderCtrl)

list(APPEND EXTRA_LIBS SpiderCtrl Spider RaspiBlocks RaspiLib BCM2835 smbus)
list(APPEND EXTRA_INCLUDES ${PROJECT_SOURCE_DIR}/SpiderCtrl/include ${PROJECT_SOURCE_DIR}/Spider/inc ${PROJECT_SOURCE_DIR}/RaspiBlocks/inc ${PROJECT_SOURCE_DIR}/RaspiLib/inc ${PROJECT_SOURCE_DIR}/BCM2835 $(PROJECT_SOURCE_DIR)/smbus/include)

add_subdirectory(Application)

#add_subdirectory(RaspiLibTest)
#add_subdirectory(SpiderTest)

#add_subdirectory(Samples/TestApp)
#add_subdirectory(Samples/BCM2835_direct)
#add_subdirectory(Samples/TestSpider)
#add_subdirectory(Samples/I2C-Test)

#enable_testing()

#add_test(
#  NAME UTest
#  COMMAND RaspiLibTest
#)

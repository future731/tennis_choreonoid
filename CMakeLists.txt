cmake_minimum_required(VERSION 2.8.3)
project(tennis_choreonoid)

find_package(catkin REQUIRED COMPONENTS
  hrpsys_choreonoid
  hrpsys_choreonoid_tutorials
  jvrc_models
  tennis
  roseus
)

#find_package(cmake_modules REQUIRED)
#catkin_package(
#  CATKIN_DEPENDS
#)

set(JVRC_RTC_DIRECTORY ${hrpsys_choreonoid_SOURCE_PREFIX})
set(JVRC_CONF_DIRECTORY ${hrpsys_choreonoid_tutorials_SOURCE_PREFIX}/config)
set(JVRC_MODELS_DIRECTORY ${jvrc_models_SOURCE_PREFIX})

configure_file(${PROJECT_SOURCE_DIR}/models/grass_court.body.in ${PROJECT_SOURCE_DIR}/models/grass_court.body @ONLY)
configure_file(${PROJECT_SOURCE_DIR}/config/JAXON_RED_TENNIS.cnoid.in ${PROJECT_SOURCE_DIR}/config/JAXON_RED_TENNIS.cnoid @ONLY)
configure_file(${PROJECT_SOURCE_DIR}/config/JAXON_RED_FOREHAND.cnoid.in ${PROJECT_SOURCE_DIR}/config/JAXON_RED_FOREHAND.cnoid @ONLY)

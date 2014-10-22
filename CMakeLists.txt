cmake_minimum_required(VERSION 2.8.3)

project(bayes_filter)

# find catkin
find_package(catkin REQUIRED)

# declare this project as a catkin package
catkin_package(
   INCLUDE_DIRS include
   LIBRARIES bayes_filter
#  CATKIN_DEPENDS
#  DEPENDS
)
# other packages neccessary
find_package(Boost REQUIRED)

set (HEADERS
    include/bayes_filter/allFilters.hpp
    include/bayes_filter/bayesException.hpp
    include/bayes_filter/bayesFlt.hpp
    include/bayes_filter/CIFlt.hpp
    include/bayes_filter/covFlt.hpp
    include/bayes_filter/infFlt.hpp
    include/bayes_filter/infRtFlt.hpp
    include/bayes_filter/itrFlt.hpp
    include/bayes_filter/matSup.hpp
    include/bayes_filter/matSupSub.hpp
    include/bayes_filter/models.hpp
    include/bayes_filter/schemeFlt.hpp
    include/bayes_filter/SIRFlt.hpp
    include/bayes_filter/uBLASmatrix.hpp
    include/bayes_filter/UDFlt.hpp
    include/bayes_filter/uLAPACK.hpp
    include/bayes_filter/unsFlt.hpp
)

set (SRCS
    src/bayesFlt.cpp
    src/bayesFltAlg.cpp
    src/CIFlt.cpp
    src/covFlt.cpp
    src/infFlt.cpp
    src/infRtFlt.cpp
    src/itrFlt.cpp
    src/matSup.cpp
    src/SIRFlt.cpp
    src/UDFlt.cpp
    src/UdU.cpp
    src/unsFlt.cpp
)

include_directories(
    ${catkin_INCLUDE_DIRS}
    ${Boost_INCLUDE_DIRS} 
    ${PROJECT_SOURCE_DIR}/include 
)

# source the files and compile the library
add_library(bayes_filter ${SRCS} ${HEADERS})



#include
set(include_dirs 
         ${PROJECT_SOURCE_DIR}/include
         ${PROJECT_SOURCE_DIR}
         ${EIGEN3_INCLUDE_DIR}
         ${Pangolin_INCLUDE_DIRS}
         ${PCL_INCLUDE_DIRS}
)

include_directories(
   ${include_dirs}
)
message("${EIGEN3_INCLUDE_DIR}")
#lib
set(libraries
         ${OpenCV_LIBS}
         ${EIGEN3_LIBS}
         ${Pangolin_LIBRARIES}
         ${PCL_LIBRARIES}
)

#orbslam2 lib
#set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/lib)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/lib)

add_library(${PROJECT_NAME}  STATIC       #SHARED
System.cc
Tracking.cc
LocalMapping.cc
LoopClosing.cc
ORBextractor.cc
ORBmatcher.cc
FrameDrawer.cc
Converter.cc
MapPoint.cc
KeyFrame.cc
Map.cc
MapDrawer.cc
Optimizer.cc
PnPsolver.cc
Frame.cc
KeyFrameDatabase.cc
Sim3Solver.cc
Initializer.cc
Viewer.cc
pointcloudmapping.cc
)

target_link_libraries(${PROJECT_NAME}
${libraries}
${PROJECT_SOURCE_DIR}/Thirdparty/DBoW2/lib/libDBoW2.so
${PROJECT_SOURCE_DIR}/Thirdparty/g2o/lib/libg2o.so
)
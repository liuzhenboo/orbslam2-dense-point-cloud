#include
set(include_dirs 
         ${PROJECT_SOURCE_DIR}/include
         ${PROJECT_SOURCE_DIR}
         ${PCL_INCLUDE_DIRS}
)

include_directories(
   ${include_dirs}
)

#lib
set(libraries
         ${OpenCV_LIBS}
         ${PCL_LIBRARIES}
)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin/examples/rgbd)

add_executable(rgbd_tum rgbd_tum.cc)
target_link_libraries(rgbd_tum ${PROJECT_NAME} ${libraries})

add_executable(rgbd_my rgbd_tum.cc)
target_link_libraries(rgbd_my ${PROJECT_NAME} ${libraries})

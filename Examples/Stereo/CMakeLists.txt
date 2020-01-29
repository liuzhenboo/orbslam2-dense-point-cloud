#include
set(include_dirs 
         ${PROJECT_SOURCE_DIR}/include
         ${PROJECT_SOURCE_DIR}
)
#message("${PROJECT_SOURCE_DIR}")
include_directories(
   ${include_dirs}
)

#lib
set(libraries
         ${OpenCV_LIBS}
)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin/examples/stereo)

add_executable(stereo_kitti stereo_kitti.cc)
target_link_libraries(stereo_kitti ${PROJECT_NAME} ${libraries})

add_executable(stereo_euroc stereo_euroc.cc)
target_link_libraries(stereo_euroc ${PROJECT_NAME} ${libraries})


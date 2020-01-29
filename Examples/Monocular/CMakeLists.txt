#include
set(include_dirs 
         ${PROJECT_SOURCE_DIR}/include
         ${PROJECT_SOURCE_DIR}
)

include_directories(
   ${include_dirs}
)

#lib
set(libraries
         ${OpenCV_LIBS}
)

# Build examples

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin/examples/monocular)

add_executable(mono_tum mono_tum.cc)
target_link_libraries(mono_tum ${PROJECT_NAME} ${libraries})

add_executable(mono_kitti mono_kitti.cc)
target_link_libraries(mono_kitti ${PROJECT_NAME} ${libraries})

add_executable(mono_euroc mono_euroc.cc)
target_link_libraries(mono_euroc ${PROJECT_NAME} ${libraries})

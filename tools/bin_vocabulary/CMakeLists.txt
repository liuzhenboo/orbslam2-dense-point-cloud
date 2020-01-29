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

# Build tools
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin/tools)
add_executable(bin_vocabulary bin_vocabulary.cpp)
target_link_libraries(bin_vocabulary ${PROJECT_SOURCE_DIR}/Thirdparty/DBoW2/lib/libDBoW2.so ${libraries} )
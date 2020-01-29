option( BUILD_bin_vocabulary "Build bin vocabulary" ON )
if(BUILD_bin_vocabulary)
   add_subdirectory("bin_vocabulary")
endif()

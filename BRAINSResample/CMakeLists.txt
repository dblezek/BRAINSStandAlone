project(BRAINSResample)
#-----------------------------------------------------------------------------
# Output directories.
#

configure_file(
  ${CMAKE_CURRENT_SOURCE_DIR}/BRAINSResampleCommonLib.h.in
  ${CMAKE_CURRENT_BINARY_DIR}/BRAINSResampleCommonLib.h
  )

###
configure_file(${BRAINSResample_SOURCE_DIR}/CTestCustom.ctest ${BRAINSResample_BINARY_DIR}/CTestCustom.ctest COPYONLY)

set(ALL_PROGS_LIST
  BRAINSResample
  )
foreach(prog ${ALL_PROGS_LIST})
  StandardBRAINSBuildMacro(NAME ${prog} TARGET_LIBRARIES BRAINSCommonLib )
endforeach()

### Add the Testing Subdirectory.
if(BUILD_TESTING)
  add_subdirectory(TestSuite)
endif(BUILD_TESTING)

project(BRAINSConstellationDetectorTool)
#-----------------------------------------------------------------------------
# Output directories.
#

add_subdirectory(src)

#-----------------------------------------------------------------------------
## optional build.

# Build test option
if(BUILD_TESTING)
  add_subdirectory(TestSuite)
endif(BUILD_TESTING)

# Build GUI option, the option is provided in src directory
if(BUILD_WITH_GUI OR BRAINS3_USE_QT OR BRAINSTools_USE_QT)
  add_subdirectory(gui)
endif()

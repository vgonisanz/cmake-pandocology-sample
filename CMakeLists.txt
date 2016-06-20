cmake_minimum_required(VERSION 3.0)

# Main Step 0: Add CMake dependencies
# ------------------------------------------------------------------------------------------------------
MESSAGE(STATUS "Adding CMake modules...")
LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake/Modules/cmake-pandocology")
INCLUDE(pandocology)
INCLUDE(cmspandoc)

# Main Step I: Create main project
# ------------------------------------------------------------------------------------------------------
SET(PROJ_MAIN_NAME "SAMPLE-PANDOCOLOGY")                   # This ID must be unique
PROJECT(${PROJ_MAIN_NAME}-main NONE)                       # Create solution project
MESSAGE(STATUS "Documentation project ${PROJ_MAIN_NAME}")

# Main Step II: Configure main pandoc variables
# ------------------------------------------------------------------------------------------------------
CONFIGUREPANDOCOLOGY()

# Main Step III: Create option for compile or not docs
# ------------------------------------------------------------------------------------------------------
# OPTION(${PROJ_MAIN_NAME}_DOC_FOO  			"Create option to compile doc FOO"  ON )
OPTION(${PROJ_MAIN_NAME}_DOC_SYNTAX  			    "Create option to compile doc with basic syntax"  ON )

# Main Step IV: Add subdirectories if option is enabled
# ------------------------------------------------------------------------------------------------------
MESSAGE(STATUS "Adding documents...")
IF(${${PROJ_MAIN_NAME}_DOC_SYNTAX} )
  ADD_SUBDIRECTORY(src/syntax)
ENDIF()

MESSAGE(STATUS "Documentation project ${${PROJ_MAIN_NAME}-main} done!")

# Step I: Set a name (PROJ_NAME)
# ------------------------------------------------------------------------------------------------------
SET(PROJ_NAME syntax)
PROJECT(${PROJ_NAME})
MESSAGE(STATUS "· ${PROJ_NAME} document added!")
MESSAGE(STATUS "· ${${PROJ_MAIN_NAME}_PATH_MAIN}/template/latex")
# Step II: create variables for pandoc
# ------------------------------------------------------------------------------------------------------
SET(${PROJ_NAME}_DOCS "doc/main.md")
SET(${PROJ_NAME}_RESOURCES img templates )                   # Must be subdirectories relative to current path
SET(${PROJ_NAME}_TEMPLATE "--template=templates/simpletemplate.tex")

# Step III: create document using pandoc
# ------------------------------------------------------------------------------------------------------
ADD_DOCUMENT(
    ${PROJ_NAME}.pdf
    SOURCES             ${${PROJ_NAME}_DOCS}
    RESOURCE_DIRS       ${${PROJ_NAME}_RESOURCES}
    #RESOURCE_FILES      references.bib
    PANDOC_DIRECTIVES   ${PANDOC_PDF_CONFIG} ${${PROJ_NAME}_TEMPLATE}
    PRODUCT_DIRECTORY   output/${PROJ_NAME}
    #DEPENDS             appendices.tex
)

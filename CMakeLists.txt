cmake_minimum_required(VERSION 2.8.4)

project(UseLATEX_DOC NONE)

include(cmake/modules/UseLATEX.cmake)

# Note that normally CMakeLists.txt would not be considered an
# input to the document, but in this special case of documenting
# UseLATEX.cmake the contents of this file is actually included
# in the document.

file(GLOB MODERNCV_FILES "moderncv/*")
file(COPY ${MODERNCV_FILES} DESTINATION ${CMAKE_BINARY_DIR})

add_latex_document(template_en.tex
    BIBFILES publications.bib
    IMAGES picture.jpg 
    FORCE_PDF
)

add_latex_document(template_ru.tex
    BIBFILES publications.bib
    IMAGES picture.jpg 
    FORCE_PDF
)


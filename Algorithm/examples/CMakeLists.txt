## Add definitions ##
add_definitions(-D_LARGEFILE_SOURCE -D_LARGE_FILES -D_FILE_OFFSET_BITS=64)

## Targets ##
include_directories("${CMAKE_CURRENT_SOURCE_DIR}/../include"
                    "${CMAKE_CURRENT_BINARY_DIR}/../include")
link_directories("${CMAKE_CURRENT_BINARY_DIR}/../lib")
foreach(src suftest mksary mkindex sasearch sabsearch sasearch-orig bwt unbwt mkbinary sabgrep bgrep finspect)
  add_executable(${src} ${src}.c)
  target_link_libraries(${src} divsufsort)
endforeach(src)

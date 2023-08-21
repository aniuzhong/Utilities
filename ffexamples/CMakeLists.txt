project(FFExamples)

file(GLOB SOURCES *.c)

message(STATUS ${SOURCES})

foreach(sourcefile ${SOURCES})
    get_filename_component(name ${sourcefile} NAME_WE)
    add_executable(${name} ${sourcefile})
    target_include_directories(${name} PRIVATE ${FFMPEG_INCLUDE_DIRS})
    target_link_libraries(${name} PRIVATE ${FFMPEG_LIBRARIES})
endforeach(sourcefile ${SOURCES})
set(TARGET_NAME placement)

file(GLOB CPP_SOURCES
        "${CMAKE_CURRENT_SOURCE_DIR}/*.cc")

set(INCLUDE_DIRS
        ${CMAKE_CURRENT_SOURCE_DIR}/..
)

set(LINK_LIBS
        database_cxx
        constraints_cxx
        wirelength_cxx
        utils_cxx
)

add_library(${TARGET_NAME}_cxx STATIC ${CPP_SOURCES})
target_link_libraries(${TARGET_NAME}_cxx ${TORCH_LIBRARIES})
target_include_directories(${TARGET_NAME}_cxx PUBLIC ${INCLUDE_DIRS})
target_link_directories(${TARGET_NAME}_cxx PUBLIC ${LINK_LIBS})


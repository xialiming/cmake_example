set(LIB01_SRC lib01.c)
add_library(lib01_shared SHARED ${LIB01_SRC})
add_library(lib01_static STATIC ${LIB01_SRC})
include_directories(${PROJECT_SOURCE_DIR}/include)

#SET_TARGET_PROPERTIES(lib01_shared PROPERTIES VERSION 1.0 SOVERSION 1)
set_target_properties(lib01_shared lib01_static PROPERTIES OUTPUT_NAME "lib01")
set_target_properties(lib01_shared lib01_static PROPERTIES CLEAN_DIRECT_OUTPUT 1)

install(TARGETS lib01_shared lib01_static 
	LIBRARY DESTINATION lib
	ARCHIVE DESTINATION lib
	)


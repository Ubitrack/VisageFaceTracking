IF(WIN32)
	set(the_description "The UbiTrack Visage Face Tracking Component")
	ut_add_component(VisageFaceTracking DEPS utcore utdataflow utvision )
	
	SET(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_CURRENT_SOURCE_DIR}/cmake")
	
	FIND_PACKAGE(Visage REQUIRED)
	
	ut_component_include_directories("src" ${Visage_INCLUDE_DIR} ${TINYXML_INCLUDE_DIR} ${LOG4CPP_INCLUDE_DIR} ${BOOSTBINDINGS_INCLUDE_DIR} ${LAPACK_INCLUDE_DIR} ${Boost_INCLUDE_DIR} ${OPENCV_INCLUDE_DIR})
	ut_glob_component_sources(HEADERS "src/*.h" SOURCES "src/*.cpp")
	ut_create_single_component(${Visage_LIBRARY})
	ut_install_utql_patterns()
ENDIF(WIN32)
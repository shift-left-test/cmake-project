add_library(sqrt SHARED src/sqrt.cpp)

target_include_directories(sqrt PUBLIC include)

set_target_properties(sqrt PROPERTIES
                      VERSION 1.0.0
                      SOVERSION 1)

install(TARGETS sqrt
        RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
        LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
	ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
	PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_OLDINCLUDEDIR})

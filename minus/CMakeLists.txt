add_library(minus STATIC minus.cpp)

target_include_directories(minus PUBLIC ${CMAKE_SOURCE_DIR})

install(TARGETS minus
        RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
        LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
        ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
        PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_OLDINCLUDEDIR})

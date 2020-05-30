add_executable(program main.cpp)

target_link_libraries(program PUBLIC plus minus)

install(TARGETS program RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR})

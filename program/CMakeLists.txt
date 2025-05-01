add_executable(program main.cpp)

target_link_libraries(program PRIVATE plus minus)

install(TARGETS program RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR})

cmake_minimum_required(VERSION 2.4.3 FATAL_ERROR )

find_package(Qt3 REQUIRED)

include_directories(${QT_INCLUDE_DIR} ${CMAKE_BINARY_DIR})

set(cutecomSrcs main.cpp qcppdialogimpl.cpp)

qt_wrap_cpp(foo cutecomSrcs qcppdialogimpl.h)

qt_wrap_ui(foo uiHeaders cutecomSrcs cutecommdlg.ui)

add_executable(cutecom ${cutecomSrcs} ${uiHeaders})
target_link_libraries(cutecom ${QT_LIBRARIES})

install(TARGETS cutecom DESTINATION bin )
install(FILES cutecom.desktop DESTINATION share/applnk/Utilities)

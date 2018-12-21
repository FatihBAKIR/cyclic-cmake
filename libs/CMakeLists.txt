add_library(a a.cpp)
add_library(b b.cpp)

target_link_libraries(a PUBLIC b)
target_link_libraries(b PUBLIC a)

install(TARGETS a DESTINATION lib/a)
install(FILES a-config.cmake DESTINATION lib/a)
install(TARGETS a EXPORT a DESTINATION lib/a)
install(EXPORT a DESTINATION lib/a)

install(TARGETS b DESTINATION lib/b)
install(FILES b-config.cmake DESTINATION lib/b)
install(TARGETS b EXPORT b DESTINATION lib/b)
install(EXPORT b DESTINATION lib/b)

include_directories(../../include)

add_library(
  digest

  OBJECT

  digest.c
  digests.c
)

add_executable(
  digest_test

  digest_test.cc

  $<TARGET_OBJECTS:test_support>
)

set_executable_props(digest_test)

target_link_libraries(digest_test crypto)
add_dependencies(all_tests digest_test)

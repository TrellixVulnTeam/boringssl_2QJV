include_directories(../../include)

add_library(
  dsa

  OBJECT

  dsa.c
  dsa_asn1.c
)

add_executable(
  dsa_test

  dsa_test.c

  $<TARGET_OBJECTS:test_support>
)

set_executable_props(dsa_test)
link_cplusplus(dsa_test)

target_link_libraries(dsa_test crypto)
add_dependencies(all_tests dsa_test)

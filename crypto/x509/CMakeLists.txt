include_directories(../../include)

add_library(
  x509

  OBJECT

  a_digest.c
  a_sign.c
  a_strex.c
  a_verify.c
  asn1_gen.c
  by_dir.c
  by_file.c
  i2d_pr.c
  pkcs7.c
  t_crl.c
  t_req.c
  t_x509.c
  t_x509a.c
  x509.c
  x509_att.c
  x509_cmp.c
  x509_d2.c
  x509_def.c
  x509_ext.c
  x509_lu.c
  x509_obj.c
  x509_r2x.c
  x509_req.c
  x509_set.c
  x509_trs.c
  x509_txt.c
  x509_v3.c
  x509_vfy.c
  x509_vpm.c
  x509cset.c
  x509name.c
  x509rset.c
  x509spki.c
  x509type.c
  x_algor.c
  x_all.c
  x_attrib.c
  x_crl.c
  x_exten.c
  x_info.c
  x_name.c
  x_pkey.c
  x_pubkey.c
  x_req.c
  x_sig.c
  x_spki.c
  x_val.c
  x_x509.c
  x_x509a.c
)

add_executable(
  pkcs7_test

  pkcs7_test.c

  $<TARGET_OBJECTS:test_support>
)

set_executable_props(pkcs7_test)
link_cplusplus(pkcs7_test)

add_executable(
  x509_test

  x509_test.cc

  $<TARGET_OBJECTS:test_support>
)

set_executable_props(x509_test)

target_link_libraries(pkcs7_test crypto)
target_link_libraries(x509_test crypto)
add_dependencies(all_tests pkcs7_test x509_test)

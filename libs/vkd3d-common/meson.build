vkd3d_common_src = files([
  'debug.c',
  'memory.c',
  'utf8.c',
])

vkd3d_common_lib = static_library('vkd3d_common', vkd3d_common_src,
  include_directories : vkd3d_include_path,
  override_options    : [ 'c_std='+vkd3d_c_std ])

vkd3d_common_dep = declare_dependency(
  link_with           : [ vkd3d_common_lib ])
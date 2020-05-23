vkd3d_utils_src = files([
  'vkd3d_utils_main.c',
])

vkd3d_utils_dll = shared_library('vkd3d_utils', vkd3d_utils_src, vkd3d_headers,
  name_prefix         : '',
  dependencies        : vkd3d_dep,
  include_directories : vkd3d_include_path,
  install             : true,
  override_options    : [ 'c_std='+vkd3d_c_std ])

vkd3d_utils_dep = declare_dependency(
  link_with           : [ vkd3d_utils_dll ],
  include_directories : vkd3d_include_path)
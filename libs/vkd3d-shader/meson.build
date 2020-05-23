vkd3d_shader_src = files([
  'checksum.c',
  'dxbc.c',
  'spirv.c',
  'trace.c',
  'vkd3d_shader_main.c',
])

vkd3d_shader_dll = shared_library('vkd3d_shader', vkd3d_shader_src, vkd3d_headers,
  name_prefix         : '',
  dependencies        : vkd3d_common_dep,
  include_directories : vkd3d_include_path,
  install             : true,
  override_options    : [ 'c_std='+vkd3d_c_std ])

vkd3d_shader_dep = declare_dependency(
  link_with           : [ vkd3d_shader_dll ],
  include_directories : vkd3d_include_path)
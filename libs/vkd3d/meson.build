vkd3d_src = [
  'command.c',
  'device.c',
  'meta.c',
  'resource.c',
  'state.c',
  'utils.c',
  'vkd3d_main.c',
]

vkd3d_dll = shared_module('vkd3d', vkd3d_src, vkd3d_version, vkd3d_headers,
  name_prefix         : '',
  dependencies        : [ vkd3d_common_dep, vkd3d_shader_dep, threads_dep ],
  include_directories : vkd3d_include_path,
  install             : true,
  override_options    : [ 'c_std='+vkd3d_c_std ])

vkd3d_dep = declare_dependency(
  link_with           : [ vkd3d_dll, vkd3d_common_lib ],
  include_directories : vkd3d_include_path)

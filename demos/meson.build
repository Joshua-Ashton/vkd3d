demo_vkd3d_deps = [
  vkd3d_dep,
  vkd3d_utils_dep,
  threads_dep,
  lib_vulkan
]

if vkd3d_platform == 'windows'
  demo_vkd3d_deps += lib_dxgi
else
  demo_vkd3d_deps += vkd3d_compiler.find_library('m')
  demo_vkd3d_deps += vkd3d_compiler.find_library('xcb')
  demo_vkd3d_deps += vkd3d_compiler.find_library('xcb-keysyms')
endif

executable('gears',    ['gears.c'],    vkd3d_headers, dependencies : demo_vkd3d_deps, install : true, gui_app : true, override_options: ['c_std='+vkd3d_c_std])
executable('triangle', ['triangle.c'], vkd3d_headers, dependencies : demo_vkd3d_deps, install : true, gui_app : true, override_options: ['c_std='+vkd3d_c_std])
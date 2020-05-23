project('vkd3d', ['c'], version : 'v1.1', meson_version : '>= 0.46')

cpu_family = target_machine.cpu_family()

vkd3d_compiler = meson.get_compiler('c')

vkd3d_c_std = 'c99'

vkd3d_include_path = include_directories('./include', './include/private', './include/external')

if (cpu_family == 'x86_64')
  vkd3d_library_path = meson.source_root() + '/lib'
else
  vkd3d_library_path = meson.source_root() + '/lib32'
endif

idl_compiler = find_program('widl')

idl_generator = generator(idl_compiler,
  output    : [ '@BASENAME@.h' ],
  arguments : [ '-h', '-o', '@OUTPUT@', '@INPUT@' ])

vkd3d_platform = target_machine.system()

threads_dep = dependency('threads')

if vkd3d_platform == 'windows'
  lib_vulkan = vkd3d_compiler.find_library('vulkan-1', dirs : vkd3d_library_path)
  lib_dxgi   = vkd3d_compiler.find_library('dxgi')
else
  lib_vulkan = vkd3d_compiler.find_library('vulkan')
endif

vkd3d_version = vcs_tag(
  command: ['git', 'describe', '--dirty=+'],
  input:  'vkd3d_version.c.in',
  output: 'vkd3d_version.c')

subdir('include')
subdir('libs')

enable_demos = get_option('enable_demos')

if enable_demos
  subdir('demos')
endif
wren_src = [
  'vm/wren_compiler.c',
  'vm/wren_core.c',
  'vm/wren_primitive.c',
  'vm/wren_utils.c',
  'vm/wren_value.c',
  'vm/wren_vm.c',
  'vm/wren_debug.c',
  'optional/wren_opt_meta.c',
  'optional/wren_opt_random.c'
]

wren_inc = include_directories('./vm')
wren_optional_inc = include_directories('./optional')
public_wren_inc = include_directories('./include')

cc = meson.get_compiler('c')
m_dep = cc.find_library('m', required : false)

wren = library('wren', wren_src, 
  include_directories: [public_wren_inc, wren_inc, wren_optional_inc], 
  dependencies: m_dep)

wren_dep = declare_dependency(link_with: wren, include_directories: public_wren_inc)

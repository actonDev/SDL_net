project('sdl_net', 'c',
	version: '2.0.1',
       )

includes = include_directories('.')
sources = files(
 'SDLnet.c',
 'SDLnetTCP.c',
 'SDLnetUDP.c',
 # 'SDLnetselect.c',
  )

sdl_net = library('sdl_net',
  sources,
  include_directories : includes,
  # c_args : core_args,
  # link_args : core_ldflags,
  dependencies : [
    dependency('sdl', required: true),
    ]
  )

sdl_net_dep = declare_dependency(
  link_with: sdl_net,
  include_directories: includes,
  )

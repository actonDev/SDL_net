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

c_args = []
link_args = []
system = build_machine.system()

if system == 'windows'
  # also see https://github.com/actonDev/SDL_net/blob/master/VisualC/SDL_net.vcxproj
  c_args += [
    # not sure if all are needed, but had problems so just.. this
    '-DWINDOWS',
    '-D__WIN32__',
    '-D_WIN64',
  ]
  # inet_addr : Ws2_32.lib
  # GetAdaptersInfo : Iphlpapi.lib
  link_args += [
    'ws2_32.lib',
    'iphlpapi.lib',
  ]
endif

sdl_net = library('sdl_net',
  sources,
  include_directories : includes,
  c_args : c_args,
  link_args : link_args,
  dependencies : [
    dependency('sdl', required: true),
    ]
  )

sdl_net_dep = declare_dependency(
  link_with: sdl_net,
  include_directories: includes,
  )

files=[
'arg.c',
'ddesc.c',
'debug.c',
'dreg.c',
'esil.c',
'map.c',
'p/bfvm.c',
'p/debug_bf.c',
#'p/debug_bochs.c',
'p/debug_esil.c',
#'p/debug_gdb.c',
'p/debug_io.c',
'p/debug_native.c',
#'p/debug_qnx.c',
'p/debug_rap.c',
#'p/debug_wind.c',
#'p/native/arm.c',
#'p/native/bt/fuzzy-all.c',
#'p/native/bt/generic-x64.c',
#'p/native/bt/generic-x86.c',
#'p/native/bt.c',
#'p/native/darwin.c',
#'p/native/drx.c',
#'p/native/maps/darwin.c',
#'p/native/maps/windows.c',
'p/native/procfs.c',
#'p/native/reg.c',
#'p/native/w32.c',
#'p/native/windows/windows_debug.c',
'pid.c',
'plugin.c',
'session.c',
'signal.c',
'snap.c',
'trace.c',
]

if host_os == 'linux'
  files += [
    'p/native/linux/linux_debug.c',
    'p/native/linux/linux_coredump.c'
  ]
endif

if host_os == 'darwin'
  files += [
    'p/native/xnu/xnu_debug.c',
#'p/native/xnu/trap_arm.c',
#'p/native/xnu/trap_x86.c',
#'p/native/xnu/xnu_excthreads.c',
#'p/native/xnu/xnu_threads.c',
  ]
endif

r_debug = shared_library('r_debug', files,
  include_directories: include_directories(['../include', '../bin/format/elf']),
  c_args: ['-DCORELIB'],
  link_with: [r_util, r_hash, r_reg, r_syscall, r_anal, r_flag, r_io, r_bp, r_search, r_cons, r_lang],
  install: true
)

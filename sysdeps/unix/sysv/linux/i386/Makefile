# The default ABI is 32.
default-abi := 32

ifeq ($(subdir),misc)
sysdep_routines += ioperm iopl vm86
endif

ifeq ($(subdir),elf)
sysdep-dl-routines += libc-do-syscall
sysdep-others += lddlibc4
install-bin += lddlibc4
endif

ifeq ($(subdir),io)
sysdep_routines += libc-do-syscall
endif

ifeq ($(subdir),nptl)
libpthread-sysdep_routines += libc-do-syscall
libpthread-shared-only-routines += libc-do-syscall
endif

ifeq ($(subdir),stdlib)
gen-as-const-headers += ucontext_i.sym
endif

ifeq ($(subdir),csu)
sysdep-dl-routines += sysdep
endif

ifeq ($(subdir),nptl)
# pull in __syscall_error routine
libpthread-routines += sysdep
libpthread-shared-only-routines += sysdep
endif

ifeq ($(subdir),rt)
# pull in __syscall_error routine
librt-routines += sysdep
librt-shared-only-routines += sysdep
endif

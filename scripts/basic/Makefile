###
# This Makefile lists the most basic programs used during the build process.
# The programs listed herein are what are needed to do the basic stuff,
# such as fix file dependencies.
# This initial step is needed to avoid files to be recompiled
# when kernel configuration changes (which is what happens when
# .config is included by main Makefile.
# ---------------------------------------------------------------------------
# fixdep: 	 Used to generate dependency information during build process

HOSTLD   = ld.lld
CC		= clang
LD		= ld.lld
AR		= llvm-ar
NM    = llvm-nm
OBJCOPY   = llvm-objcopy
OBJDUMP		= llvm-objdump
READELF		= llvm-readelf
OBJSIZE		= llvm-size
STRIP		= llvm-strip

HOST_EXTRACFLAGS += -I/usr/include/
hostprogs-y	:= fixdep
always		:= $(hostprogs-y)

# fixdep is needed to compile other host programs
$(addprefix $(obj)/,$(filter-out fixdep,$(always))): $(obj)/fixdep

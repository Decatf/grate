lib_LTLIBRARIES = libgrate-wrap.la

libgrate_wrap_la_CPPFLAGS = \
	-I$(top_srcdir)/include \
	-I$(top_srcdir)/src/libgrate

if ENABLE_RNN
libgrate_wrap_la_CPPFLAGS += -DENABLE_RNN
endif

if ENABLE_ZLIB
libgrate_wrap_la_CPPFLAGS += -DENABLE_ZLIB
endif

if ENABLE_LZ4
libgrate_wrap_la_CPPFLAGS += -DENABLE_LZ4
endif

libgrate_wrap_la_CFLAGS = -pthread $(ZLIB_CFLAGS) $(LZ4_CFLAGS)

libgrate_wrap_la_SOURCES = \
	cdma_parser.c \
	cdma_parser.h \
	cgdrv.c \
	disasm.h \
	disasm.c \
	drm.h \
	drm_fourcc.h \
	drm_mode.h \
	host1x.c \
	host1x.h \
	nvhost.c \
	nvhost.h \
	recorder.c \
	recorder.h \
	syscall.c \
	syscall.h \
	tegra_drm.h \
	utils.c \
	utils.h

AUTOMAKE_OPTIONS = subdir-objects

libgrate_wrap_la_SOURCES += \
	../libgrate/asm.h \
	../libgrate/fragment_asm.h \
	../libgrate/fragment_disasm.c \
	../libgrate/linker_asm.h \
	../libgrate/linker_disasm.c \
	../libgrate/vertex_disasm.c \
	../libgrate/vpe_vliw.h

libgrate_wrap_la_LIBADD = -ldl
if ENABLE_RNN
libgrate_wrap_la_LIBADD += -lrnn -lenvyutil -lxml2
endif
if ENABLE_ZLIB
libgrate_wrap_la_LIBADD += -lz
endif
if ENABLE_LZ4
libgrate_wrap_la_LIBADD += -llz4
endif


if WANT_JANSSON
JANSSON_INCLUDES= -I$(top_srcdir)/compat/jansson
else
JANSSON_INCLUDES=
endif

EXTRA_DIST	= example-cfg.json nomacro.pl

SUBDIRS		= compat

INCLUDES	= $(PTHREAD_FLAGS) -fno-strict-aliasing $(JANSSON_INCLUDES)

bin_PROGRAMS	= minerd

dist_man_MANS	= minerd.1

minerd_SOURCES	= 	\
					elist.h miner.h compat.h \
					cpu-miner.c util.c \
					sha2.c scrypt.c \
					argon2d/blake2-impl.h \
					argon2d/blake2.h \
					argon2d/blamka-round-opt.h \
					argon2d/blamka-round-ref.h \
					argon2d/blake2b.c \
					argon2d/argon2.h \
					argon2d/core.h \
					argon2d/encoding.h \
					argon2d/thread.h \
					argon2d/opt.h \
					argon2d/argon2.c \
					argon2d/core.c \
					argon2d/encoding.c \
					argon2d/thread.c \
					argon2d/opt.c \
					  sha3/sph_keccak.c \
  sha3/sph_hefty1.c \
  sha3/sph_groestl.c \
  sha3/sph_skein.c \
  sha3/sph_bmw.c \
  sha3/sph_jh.c \
  sha3/sph_shavite.c \
  sha3/sph_blake.c \
  sha3/mod_blakecoin.c \
  sha3/sph_luffa.c \
  sha3/sph_cubehash.c \
  sha3/sph_simd.c \
  sha3/sph_echo.c \
  sha3/sph_hamsi.c \
  sha3/sph_haval.c \
  sha3/sph_fugue.c \
  sha3/sph_ripemd.c \
  sha3/sph_sha2.c \
  sha3/sph_sha2big.c \
  sha3/sph_shabal.c \
  sha3/sph_whirlpool.c \
  sha3/gost_streebog.c 



if USE_ASM
if ARCH_x86
minerd_SOURCES += sha2-x86.S scrypt-x86.S
endif
if ARCH_x86_64
minerd_SOURCES += sha2-x64.S scrypt-x64.S
endif
if ARCH_ARM
minerd_SOURCES += sha2-arm.S scrypt-arm.S
endif
if ARCH_PPC
minerd_SOURCES += sha2-ppc.S scrypt-ppc.S
endif
endif
minerd_LDFLAGS	= $(PTHREAD_FLAGS)
minerd_LDADD	= @LIBCURL@ @JANSSON_LIBS@ @PTHREAD_LIBS@ @WS2_LIBS@
minerd_CPPFLAGS = @LIBCURL_CPPFLAGS@


#
# nxQuake Makefile for SDL (Linux)
# This will probably work on other Unix systems where sdl-config is present, but
# won't work on Windows - use s_win32 instead
# August 2004
#

CC = gcc
CFLAGS = -I../common/include -I../r_soft/include -Iinclude `sdl-config --cflags` -O2
LIBS = -lm `sdl-config --libs` -lSDL_net
TARGET = nxquake

COMMON_OBJS = chase.o cl_demo.o cl_input.o cl_main.o cl_parse.o cl_tent.o cmd.o
COMMON_OBJS += common.o console.o crc.o cvar.o host.o host_cmd.o
COMMON_OBJS += keys.o mathlib.o menu.o net_dgrm.o net_loop.o net_main.o net_vcr.o
COMMON_OBJS += nonintel.o pr_cmds.o pr_edict.o pr_exec.o r_part.o sbar.o
COMMON_OBJS += sv_main.o sv_move.o sv_phys.o sv_user.o view.o wad.o
COMMON_OBJS += world.o zone.o
COMMON_OBJS += snd_dma.o snd_mem.o snd_mix.o

SOFT_OBJS = d_edge.o d_fill.o d_init.o d_modech.o d_part.o d_polyse.o d_scan.o
SOFT_OBJS += d_sky.o d_sprite.o d_surf.o d_vars.o d_zpoint.o draw.o r_aclip.o
SOFT_OBJS += r_alias.o r_bsp.o r_draw.o r_edge.o r_efrag.o r_light.o r_main.o
SOFT_OBJS += r_misc.o r_sky.o r_sprite.o r_surf.o r_vars.o model.o screen.o

SYS_OBJS = cd_sdl.o in_sdl.o net_sdl.o net_sdludp.o snd_sdl.o sys_sdl.o vid_sdl.o

OBJS = $(COMMON_OBJS) $(SOFT_OBJS) $(SYS_OBJS)

all: $(TARGET)

clean:
	-rm -f $(TARGET) $(OBJS)

$(TARGET): $(OBJS)
	$(CC) $(CFLAGS) $(LDFLAGS) -o $(TARGET) $(OBJS) $(LIBS)

%.o: src/%.c
	$(CC) $(CFLAGS) -c $< -o $@

%.o: ../common/src/%.c
	$(CC) $(CFLAGS) -c $< -o $@

%.o: ../r_soft/src/%.c
	$(CC) $(CFLAGS) -c $< -o $@

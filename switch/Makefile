#---------------------------------------------------------------------------------
.SUFFIXES:
#---------------------------------------------------------------------------------

ifeq ($(strip $(DEVKITPRO)),)
$(error "Please set DEVKITPRO in your environment. export DEVKITPRO=<path to>/devkitpro")
endif

ifeq ($(OS),Windows_NT)
MAKEPKG	:=	makepkg
else
ifeq (,$(shell which makepkg))
MAKEPKG	:=	dkp-makepkg
else
MAKEPKG	:=	makepkg
endif
endif

all: mpv sqlite

.PHONY: harfbuzz
harfbuzz:
	@echo Installing harfbuzz
	@cd harfbuzz; $(MAKEPKG) -c -C -f -i -s --noconfirm; cd ..

.PHONY: freetype
freetype:
	@echo Installing freetype
	@cd freetype; $(MAKEPKG) -c -C -f -i -s --noconfirm; cd ..

.PHONY: libass
libass: harfbuzz freetype
	@echo Installing libass
	@cd libass; $(MAKEPKG) -c -C -f -i -s --noconfirm; cd ..

.PHONY: libnfs
libnfs:
	@echo Installing libnfs
	@cd libnfs; $(MAKEPKG) -c -C -f -i -s --noconfirm; cd ..

.PHONY: libsmb2
libsmb2:
	@echo Installing libsmb2
	@cd libsmb2; $(MAKEPKG) -c -C -f -i -s --noconfirm; cd ..

.PHONY: ffmpeg
ffmpeg: libass libnfs libsmb2
	@echo Installing ffmpeg
	@cd ffmpeg; $(MAKEPKG) -c -C -f -i -s --noconfirm; cd ..

.PHONY: mpv
mpv: ffmpeg
	@echo Installing libmpv
	@cd libmpv; $(MAKEPKG) -c -C -f -i -s --noconfirm; cd ..

.PHONY: sqlite
sqlite:
	@echo Installing sqlite
	@cd sqlite; $(MAKEPKG) -c -C -f -i -s --noconfirm; cd ..

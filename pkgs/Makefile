MAKEPKG = makepkg -cs
REPOADD = repo-add

PKGNAMES = librewolf maxfetch nvm vscodium
PKGS     = librewolf-*.pkg.tar.xz maxfetch-*.pkg.tar.zst nvm-*.pkg.tar.zst vscodium-*.pkg.tar.xz
#GPGKEY   = CD735FBFF84E7729B27F88E65222945A86F1670C

all: virbos.db.tar.xz

virbos.db.tar.xz: ${PKGS}
	${REPOADD} -R -n -s virbos.db.tar.xz ${PKGS}

librewolf-*.pkg.tar.xz:
	${MAKE} -C../librewolf
	cd ../librewolf && PKGDEST="../pkgs" PKGEXT=".pkg.tar.xz" ${MAKEPKG}

maxfetch-*.pkg.tar.zst:
	${MAKE} -C../maxfetch
	cd ../maxfetch && PKGDEST="../pkgs" ${MAKEPKG}

nvm-*.pkg.tar.zst:
	${MAKE} -C../nvm
	cd ../nvm && PKGDEST="../pkgs" ${MAKEPKG}

vscodium-*.pkg.tar.xz:
	${MAKE} -C../vscodium
	cd ../vscodium && PKGDEST="../pkgs" PKGEXT=".pkg.tar.xz" ${MAKEPKG}

clean:
	rm -f virbos.db* virbos.files* ${PKGS}
	for pkg in ${PKGS}; do rm -f "$$pkg".sig; done
	for pkg in ${PKGNAMES}; do make -C../$$pkg clean; done


.PHONY: clean

# vi: ft=make

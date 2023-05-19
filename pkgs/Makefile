MAKEPKG = makepkg -cs --nosign
REPOADD = repo-add

PKGNAMES = librewolf maxfetch nvm vscodium
PKGS     = librewolf-*.pkg.tar.xz maxfetch-*.pkg.tar.zst nvm-*.pkg.tar.zst vscodium-*.pkg.tar.xz

all: virbos.db

virbos.db: ${PKGS}
	${REPOADD} virbos.db.tar.xz ${PKGS}
	rm -f virbos.db virbos.files
	mv virbos.db.tar.xz virbos.db
	mv virbos.files.tar.xz virbos.files
	rm -f *.sig

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
	for pkg in ${PKGNAMES}; do make -C../$$pkg clean; done

.PHONY: clean

# vi: ft=make

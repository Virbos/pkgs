MAKEPKG = makepkg -cs --nosign
REPOADD = repo-add

PKGNAMES = librewolf maxfetch nvm virbos-livescripts vscodium vscodium-marketplace
PKGS     = librewolf-*.pkg.tar.xz maxfetch-*.pkg.tar.zst nvm-*.pkg.tar.zst virbos-livescripts-*.pkg.tar.zst vscodium-*.pkg.tar.xz vscodium-marketplace-*.pkg.tar.zst

all: virbos.db

virbos.db: ${PKGS}
	${REPOADD} virbos.db.tar.xz ${PKGS}
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

virbos-livescripts-*.pkg.tar.zst:
	${MAKE} -C../virbos-livescripts
	cd ../virbos-livescripts && PKGDEST="../pkgs" ${MAKEPKG}

vscodium-*.pkg.tar.xz:
	${MAKE} -C../vscodium
	cd ../vscodium && PKGDEST="../pkgs" PKGEXT=".pkg.tar.xz" ${MAKEPKG}

vscodium-marketplace-*.pkg.tar.zst:
	${MAKE} -C../vscodium-marketplace
	cd ../vscodium-marketplace && PKGDEST="../pkgs" ${MAKEPKG}

clean:
	rm -f virbos.db* virbos.files* ${PKGS}
	for pkg in ${PKGNAMES}; do make -C../$$pkg clean; done

.PHONY: clean

# vi: ft=make

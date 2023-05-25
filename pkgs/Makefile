MAKEPKG = makepkg -cs --nosign
REPOADD = repo-add

PKGNAMES = alacritty-sixel librewolf ly maxfetch ninvaders nvm \
		   virbos-livescripts virbos-logos virbos-utils vscodium \
		   vscodium-marketplace yay
PKGS     = alacritty-sixel-*.pkg.tar.zst librewolf-*.pkg.tar.xz ly-*.pkg.tar.zst \
		   maxfetch-*.pkg.tar.zst ninvaders-*.pkg.tar.zst nvm-*.pkg.tar.zst \
		   virbos-livescripts-*.pkg.tar.zst virbos-logos-*.pkg.tar.zst \
		   virbos-utils-*.pkg.tar.zst vscodium-*.pkg.tar.xz \
		   vscodium-marketplace-*.pkg.tar.zst yay-*.pkg.tar.zst

all: virbos.db

virbos.db: ${PKGS}
	${REPOADD} virbos.db.tar.xz ${PKGS}
	rm -f *.sig

alacritty-sixel-*.pkg.tar.zst:
	${MAKE} -C../alacritty-sixel
	cd ../alacritty-sixel && PKGDEST="../pkgs" ${MAKEPKG}

librewolf-*.pkg.tar.xz:
	${MAKE} -C../librewolf
	cd ../librewolf && PKGDEST="../pkgs" PKGEXT=".pkg.tar.xz" ${MAKEPKG}

ly-*.pkg.tar.zst:
	${MAKE} -C../ly
	cd ../ly && PKGDEST="../pkgs" ${MAKEPKG}

maxfetch-*.pkg.tar.zst:
	${MAKE} -C../maxfetch
	cd ../maxfetch && PKGDEST="../pkgs" ${MAKEPKG}

nvm-*.pkg.tar.zst:
	${MAKE} -C../nvm
	cd ../nvm && PKGDEST="../pkgs" ${MAKEPKG}

ninvaders-*.pkg.tar.zst:
	${MAKE} -C../ninvaders
	cd ../ninvaders && PKGDEST="../pkgs" ${MAKEPKG}

virbos-livescripts-*.pkg.tar.zst:
	${MAKE} -C../virbos-livescripts
	cd ../virbos-livescripts && PKGDEST="../pkgs" ${MAKEPKG}

virbos-logos-*.pkg.tar.zst:
	${MAKE} -C../virbos-logos
	cd ../virbos-logos && PKGDEST="../pkgs" ${MAKEPKG}

virbos-utils-*.pkg.tar.zst:
	${MAKE} -C../virbos-utils
	cd ../virbos-utils && PKGDEST="../pkgs" ${MAKEPKG}

vscodium-*.pkg.tar.xz:
	${MAKE} -C../vscodium
	cd ../vscodium && PKGDEST="../pkgs" PKGEXT=".pkg.tar.xz" ${MAKEPKG}

vscodium-marketplace-*.pkg.tar.zst:
	${MAKE} -C../vscodium-marketplace
	cd ../vscodium-marketplace && PKGDEST="../pkgs" ${MAKEPKG}

yay-*.pkg.tar.zst:
	${MAKE} -C../yay
	cd ../yay && PKGDEST="../pkgs" ${MAKEPKG}

clean:
	rm -f virbos.db* virbos.files* ${PKGS}
	for pkg in ${PKGNAMES}; do make -C../$$pkg clean; done

.PHONY: clean

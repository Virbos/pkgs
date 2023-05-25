PKG = alacritty-sixel-git

PKGBUILD:
	git clone --depth=1 https://aur.archlinux.org/${PKG}.git
	cp -f ${PKG}/PKGBUILD .
	sed -i 's/-git//g' PKGBUILD
	rm -rf ${PKG}

clean:
	rm -rf PKGBUILD src pkg *.pkg.tar.*

.PHONY: clean

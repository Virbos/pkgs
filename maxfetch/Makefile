PKG = maxfetch

PKGBUILD:
	git clone https://aur.archlinux.org/${PKG}.git ${PKG}-aur
	cp -f ${PKG}-aur/PKGBUILD .
	rm -rf ${PKG}-aur

clean:
	rm -rf PKGBUILD src pkg *.pkg.tar.* maxfetch

.PHONY: clean

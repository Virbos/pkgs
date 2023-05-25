_PKG = logos
PKG  = virbos-logos

PKGBUILD:
	git clone --depth=1 https://github.com/Virbos/${_PKG}.git ${PKG}
	cp -f ${PKG}/PKGBUILD .
	rm -rf ${PKG}

clean:
	rm -rf PKGBUILD src pkg *.pkg.tar.*

.PHONY: clean

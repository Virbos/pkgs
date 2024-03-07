PKG = virbos-logos

PKGBUILD:
	git clone --depth=1 https://github.com/Virbos/${PKG}.git
	cp -f ${PKG}/PKGBUILD .
	rm -rf ${PKG}

clean:
	rm -rf PKGBUILD src pkg *.pkg.tar.* ${PKG}

.PHONY: clean

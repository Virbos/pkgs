PKG = ttf-maple

PKGBUILD:
	git clone --depth=1 https://aur.archlinux.org/${PKG}.git
	cp -f ${PKG}/PKGBUILD .
	patch -p0 -i pkgbuild.diff
	rm -rf ${PKG}

clean:
	rm -rf PKGBUILD src pkg *.pkg.tar.* ttf-maple-*.zip ttf-maple-mono-LICENSE

.PHONY: clean

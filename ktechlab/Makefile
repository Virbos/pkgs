PKG  = ktechlab
DIFF = pkgbuild.diff

PKGBUILD:
	git clone --depth=1 https://aur.archlinux.org/${PKG}.git
	cp -f ${PKG}/PKGBUILD .
	patch <${DIFF}
	rm -rf ${PKG}

clean:
	rm -rf PKGBUILD src pkg *.pkg.tar.* ktechlab-*.tar.xz

.PHONY: clean

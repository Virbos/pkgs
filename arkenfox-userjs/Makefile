PKG = arkenfox-user.js

PKGBUILD:
	git clone --depth=1 https://aur.archlinux.org/${PKG}.git
	cp -f ${PKG}/PKGBUILD .
	cp -f ${PKG}/01-updater.patch .
	cp -f ${PKG}/02-cleaner.patch .

	patch -p0 -i arkenfox-userjs.diff
	rm -rf ${PKG}

clean:
	rm -rf PKGBUILD src pkg *.pkg.tar.* ${PKG} \
		pkg-readme 0*-*.patch arkenfox-user.js-*.tar.gz

.PHONY: clean

PKG  = ttf-maple
DIFF = pkgbuild.diff

PKGBUILD:
	git clone --depth=1 https://aur.archlinux.org/${PKG}.git
	cp -f ${PKG}/PKGBUILD .
	patch <${DIFF}
	rm -rf ${PKG}

clean:
	rm -rf PKGBUILD src pkg *.pkg.tar.* ttf-maple-*.zip ttf-maple-mono-LICENSE

.PHONY: clean

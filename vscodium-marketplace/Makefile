PKG = vscodium-bin-marketplace

PKGBUILD:
	git clone --depth=1 https://aur.archlinux.org/${PKG}.git
	cp -f ${PKG}/{PKGBUILD,patch.py} .
	cp -f ${PKG}/vscodium-bin-marketplace.hook ./vscodium-marketplace.hook
	cp -f ${PKG}/vscodium-bin-marketplace.install ./vscodium-marketplace.install
	sed -i 's/-bin//g' PKGBUILD
	rm -rf ${PKG}

clean:
	rm -rf PKGBUILD src pkg *.pkg.tar.* patch.py vscodium-marketplace.{hook,install}

.PHONY: clean

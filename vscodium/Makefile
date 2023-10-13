PKG = vscodium-bin

PKGBUILD:
	git clone --depth=1 https://aur.archlinux.org/${PKG}.git
	cp -f ${PKG}/PKGBUILD .
	cp -f ${PKG}/vscodium-bin.sh ./vscodium.sh
	cp -f ${PKG}/vscodium-bin.desktop ./vscodium.desktop
	cp -f ${PKG}/vscodium-bin-wayland.desktop ./vscodium-wayland.desktop
	cp -f ${PKG}/vscodium-bin.install ./vscodium.install
	cp -f ${PKG}/vscodium-bin-uri-handler.desktop ./vscodium-uri-handler.desktop
	sed -i 's/-bin//' PKGBUILD
	rm -rf ${PKG}

clean:
	rm -rf PKGBUILD src pkg *.pkg.tar.* vscodium.sh vscodium.desktop vscodium.install vscodium-uri-handler.desktop VSCodium-*.tar.gz

.PHONY: clean

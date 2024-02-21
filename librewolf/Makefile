PKG = librewolf-bin

PKGBUILD:
	git clone --depth=1 https://aur.archlinux.org/${PKG}.git
	cp -f ${PKG}/{PKGBUILD,default*x*.png,librewolf.desktop} .
	cp -f ${PKG}/librewolf-bin.install ./librewolf.install
	sed -i 's/-bin//' PKGBUILD
	rm -rf ${PKG}

clean:
	rm -rf PKGBUILD src pkg *.pkg.tar.* librewolf-*.tar.* default*x*.png librewolf.desktop librewolf.install source

.PHONY: clean

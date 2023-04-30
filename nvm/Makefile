PKG = nvm

PKGBUILD:
	git clone https://aur.archlinux.org/${PKG}.git
	cp -f ${PKG}/{PKGBUILD,init-nvm.sh,install-nvm-exec,nvm.install,update.sh} .
	rm -rf ${PKG}

clean:
	rm -rf PKGBUILD src pkg *.pkg.tar.* init-nvm.sh install-nvm-exec nvm-*.tar.gz nvm.install update.sh

.PHONY: clean

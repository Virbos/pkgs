# Template makefile
PKG = pkgname

PKGBUILD:
	# feel free to change this git clone url
	git clone --depth=1 https://aur.archlinux.org/${PKG}.git
	# copy all needed files here
	cp -f ${PKG}/PKGBUILD .
	# patch files here
	#sed -i 's/-bin//g' PKGBUILD
	# remove the original directory (no longer needed)
	rm -rf ${PKG}

clean:
	# add any extra files that need to be removed here
	rm -rf PKGBUILD src pkg *.pkg.tar.* myextrafile

.PHONY: clean

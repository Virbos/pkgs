MAKEPKG = makepkg -cs --noconfirm --nosign
REPOADD = repo-add

PKGS   = callisto             \
         ktechlab             \
         lite-xl              \
         ly                   \
         maxfetch             \
         ninvaders            \
         nvm                  \
         ttf-maple-mono       \
         virbos-livescripts   \
         virbos-logos         \
         virbos-utils         \
         vscodium-marketplace \
         yay
XZPKGS = librewolf vscodium

all: virbos.db

pkgs:
	@for pkg in ${PKGS}; do                           \
		printf "==> %s\n" "$$pkg";                    \
		if [ -e "$$pkg"-*-*.pkg.tar.zst ]; then       \
			continue; fi;                             \
		${MAKE} -C../"$$pkg";                         \
		cd ../"$$pkg"; PKGDEST=../pkgs ${MAKEPKG}     \
			|| exit 1;                                \
	done
	@for pkg in ${XZPKGS}; do                                         \
		if [ -e "$$pkg"-*-*.pkg.tar.xz ]; then                        \
			printf "==> %s\n" "$$pkg"; continue; fi;                  \
		printf "==> Building xz package '%s'\n" "$$pkg";              \
		${MAKE} -C../"$$pkg";                                         \
		cd ../"$$pkg"; PKGDEST=../pkgs PKGEXT=.pkg.tar.xz ${MAKEPKG}  \
			|| exit 1;                                                \
	done

virbos.db: pkgs
	${REPOADD} virbos.db.tar.xz \
		$(foreach pkg,${PKGS},${pkg}-*.pkg.tar.zst) \
		$(foreach pkg,${XZPKGS},${pkg}-*.pkg.tar.xz)

clean:
	rm -f virbos.db* virbos.files* \
		$(foreach pkg,${PKGS},${pkg}-*.pkg.tar.zst) \
		$(foreach pkg,${XZPKGS},${pkg}-*.pkg.tar.xz)
	for pkg in ${PKGS}; do make -s -C../$$pkg clean; done

.PHONY: all clean pkgs

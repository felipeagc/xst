# Maintainer: Felipe Costa <felipeagc2 at gmail [dot] com >
# derived from st-git aur package.

_pkgname=xst
pkgname=${_pkgname}-git
pkgver=20190228.3bb95d7
pkgrel=1
pkgdesc='st fork fork with xresources support and other patches'
url='https://github.com/felipeagc/xst'
arch=('i686' 'x86_64')
license=('MIT')
depends=('libxft')
makedepends=('ncurses' 'libxext' 'git')
source=("git://github.com/felipeagc/${_pkgname}.git")
sha1sums=('SKIP')

provides=(
	${_pkgname}
)
conflicts=(
	"${_pkgname}"
)

pkgver() {
	cd "${srcdir}/${_pkgname}"
	git log -1 --format='%cd.%h' --date=short | tr -d -
}

build() {
	cd "${srcdir}/${_pkgname}"
	make
}

package() {
	cd "${srcdir}/${_pkgname}"
	make PREFIX=/usr DESTDIR="${pkgdir}" install
	install -Dm644 doc/LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
	install -Dm644 README.md "${pkgdir}/usr/share/doc/${pkgname}/README"
}

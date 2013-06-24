# Maintainer: Gaetan Bisson <bisson@archlinux.org>
# Contributor: Scytrin dai Kinthra <scytrin@gmail.com>

pkgname=st-git
_pkgname=st
epoch=1
pkgver=git
pkgrel=1
pkgdesc='Simple virtual terminal emulator for X'
url='https://github.com/manpages/st.git'
arch=('i686' 'x86_64' 'armv7h')
license=('MIT')
depends=('libxft')
makedepends=('ncurses' 'libxext' 'git')
source=('https://github.com/manpages/st/archive/master.tar.gz')
sha1sums=('SKIP')

provides=("${_pkgname}")
conflicts=("${_pkgname}")

prepare() {
  mv "${srcdir}/${_pkgname}-master" "${srcdir}/${_pkgname}"
}

build() {
	cd "${srcdir}/${_pkgname}"
	make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
	cd "${srcdir}/${_pkgname}"
	make PREFIX=/usr DESTDIR="${pkgdir}" TERMINFO="${pkgdir}/usr/share/terminfo" install
	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
	install -Dm644 README "${pkgdir}/usr/share/doc/${pkgname}/README"
}

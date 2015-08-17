# Maintainer: kusakata <shohei atmark kusakata period com>

pkgname=urg_library
pkgver=1.1.8
pkgrel=1
pkgdesc='A library to use scanning range sensors of Hokuyo Automatic Corporation'
arch=('i686' 'x86_64')
url="http://sourceforge.net/p/urgnetwork/wiki/Home/"
license=('custom')
depends=('bash' 'gcc-libs')
source=("http://downloads.sourceforge.net/project/urgnetwork/urg_library/urg_library-${pkgver}.zip" "urg_serial.patch")

prepare() {
	cd "${srcdir}/urg_library-${pkgver}/src"
	patch < "${srcdir}/urg_serial.patch"
}

build() {
	cd "${srcdir}/urg_library-${pkgver}"
	make
}

package() {
	cd "${srcdir}/urg_library-${pkgver}"
	make PREFIX="${pkgdir}/usr" install
	install -Dm644 COPYRIGHT.txt "${pkgdir}/usr/share/licenses/${pkgname}/COPYRIGHT.txt"
}

md5sums=('508fba166ecc5b882a96befd520cceb5'
         'e2d04cc434edec545f40f1c117812a97')

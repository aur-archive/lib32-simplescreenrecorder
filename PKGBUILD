pkgname=lib32-simplescreenrecorder
pkgver=0.3.0
pkgrel=1
pkgdesc="OpenGL recording of 32-bit applications with SimpleScreenRecorder."
arch=("x86_64")
url="http://www.maartenbaert.be/simplescreenrecorder/"
license=("GPL3")
source=("git+https://github.com/MaartenBaert/ssr.git#tag=0.3.0")
md5sums=("SKIP")
depends=("lib32-libgl" "lib32-glu" "lib32-libx11" "lib32-libxfixes" "lib32-libxext")
makedepends=("git" "gcc-multilib")
options=("!libtool")
install=lib32-simplescreenrecorder.install

build() {
	cd "${srcdir}/ssr"
	export CC="gcc -m32"
	export CXX="g++ -m32"
	export PKG_CONFIG_PATH="/usr/lib32/pkgconfig"
	./configure --prefix=/usr --libdir=/usr/lib32 --disable-ssrprogram --disable-assert
	make
}
package() {
	cd "${srcdir}/ssr"
	make DESTDIR="${pkgdir}" install
}

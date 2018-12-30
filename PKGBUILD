# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-screensaver-biogenesis
epoch=1
pkgver=2.1.0
_codename=Leia
pkgrel=5
pkgdesc="BioGenesis screensaver for Kodi"
arch=('x86_64')
url='https://github.com/xbmc/screensaver.biogenesis'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-screensaver')
depends=('kodi')
makedepends=('cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/xbmc/screensaver.biogenesis/archive/$pkgver-$_codename.tar.gz")
sha512sums=('17f51c7f4fde44862b45caeafa5fefa315714f9e646355a772285ee455321189425100a45a3f743a0ef94bccb6106371865afeac2a2edd411ce6f392bc06c571')

build() {
    cd "screensaver.biogenesis-$pkgver-$_codename"
    cmake \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_SHARED_LIBS=1 \
        -DUSE_LTO=1
    make
}

package() {
    cd "screensaver.biogenesis-$pkgver-$_codename"
	make DESTDIR="$pkgdir/" install
}


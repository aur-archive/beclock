# Maintainer: laloch <lalochcz@gmail.com>
# Contributor: Flamelab <panosfilip@gmail.com>

pkgname=beclock
_realname=beclock-kwin-fx
pkgver=0.18
pkgrel=2
pkgdesc="A simple clock, implemented as KWin Effect"
arch=('i686' 'x86_64')
url="http://kde-look.org/content/show.php?content=117542"
depends=('kdebase-workspace>=4.6.0')
makedepends=('cmake' 'automoc4' 'gcc')
source=("http://kde-look.org/CONTENT/content-files/117542-${_realname}-${pkgver}.txz")
license=('GPL')
install=${pkgname}.install
md5sums=('7a2286008e692af62a55b8da4e5629f5')

build() {
  rm -rf ${srcdir}/${_realname}-build
  mkdir ${srcdir}/${_realname}-build
  cd ${srcdir}/${_realname}-build
  cmake ${srcdir}/${_realname}-${pkgver} \
    -DCMAKE_INSTALL_PREFIX=`kde4-config --prefix` \
    -DCMAKE_BUILD_TYPE=Release
  make
}

package() {
  cd ${srcdir}/${_realname}-build
  make DESTDIR=$pkgdir install
}

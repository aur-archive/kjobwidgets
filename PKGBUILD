# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kjobwidgets
pkgver=4.99.0
pkgrel=1
pkgdesc='KJobWidgets'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kjobwidgets'
license=('LGPL')
depends=('kcoreaddons' 'kwidgetsaddons' 'qt5-x11extras')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('663d6e6e59aa2d3bea24056e2b2cf7b8')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}

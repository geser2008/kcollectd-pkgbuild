# Maintainer: h8red  h8red at yandex dot ru
# Maintainer: geser2008  distselemov at gmail dot com
pkgname=kcollectd
pkgver=0.12.1
pkgrel=3
pkgdesc="Kcollectd is a small applications that allows to view rrd datacollections that have been created by collectd."
arch=('i686' 'x86_64')
url="https://www.antonioerusso.com/projects/kcollectd/"
license=('LGPL')
groups=()
depends=('collectd' 'boost-libs' 'rrdtool')
makedepends=('gcc' 'cmake' 'boost')
provides=()
conflicts=()
replaces=()
backup=()
options=()
source=(https://gitlab.com/aerusso/kcollectd/-/archive/v$pkgver/$pkgname-v$pkgver.tar.gz)
noextract=()
md5sums=('759c797ff9db0829fd11707132666582')
build() {
  cd $srcdir
   cd $pkgname-v$pkgver
  mkdir build && cd build
  cmake -DCMAKE_INSTALL_PREFIX=`kf5-config --prefix` .. || return 1
  make || return 1
}
package() {
  cd "$srcdir/$pkgname-v$pkgver/"
  make -C build DESTDIR="$pkgdir/" install || return 1
}

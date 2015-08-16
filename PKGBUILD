# Maintainer: Boohbah <boohbah at gmail.com>
# Contributor: ilikenwf/ Matt Parnell <parwok@gmail.com>

pkgname=libxi-git
_gitname=libXi
pkgver=1.7.2.1.gc4b261d
pkgrel=1
pkgdesc="X11 Input extension library (git version)"
arch=('i686' 'x86_64')
url="http://xorg.freedesktop.org/"
depends=('libxext-git' 'inputproto-git')
makedepends=('pkgconfig' 'xorg-util-macros' 'libxfixes')
provides=('libxi='${pkgver%%.g*})
conflicts=('libxi')
options=('!libtool')
license=('custom')
source=('git://anongit.freedesktop.org/git/xorg/lib/libXi')
md5sums=('SKIP')

pkgver() {
  cd $_gitname
  git describe --always | sed 's/libXi-//;  s/-/./g'
}

build() {
  cd $_gitname
  ./autogen.sh --prefix=/usr
  make
}

package() {
  cd $_gitname
  make DESTDIR="$pkgdir" install
}

# vim:set ts=2 sw=2 et:

# Maintainer: Doug Newgard <scimmia22 at outlook dot com>
# Contributor: twa022 <twa022 at gmail dot com>

pkgname=eve-svn
_pkgname=eve
pkgver=84552
pkgrel=1
pkgdesc="Lightweight browser based on WebKit and EFL"
arch=('i686' 'x86_64')
url="http://www.enlightenment.org"
license=('LGPL3')
depends=("elementary>=1.7.99" 'ewebkit-svn')
makedepends=('subversion')
options=('!libtool')
source=("svn+http://svn.enlightenment.org/svn/e/trunk/$_pkgname")
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$_pkgname"

  LC_ALL=C svn info | awk '/Last Changed Rev/ {print $4}'
}

build() {
  cd "$srcdir/$_pkgname"

  ./autogen.sh --prefix=/usr

  make
}

package() {
  cd "$srcdir/$_pkgname"

  make DESTDIR="$pkgdir" install
}

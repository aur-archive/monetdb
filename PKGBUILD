# Maintainer: Brian Hood <brianh6854@googlemail.com>
# Contributor: Benjamin van der Burgh <gringo@archlinux.info>

pkgname=monetdb
pkgver=11.19.15
pkgrel=1
pkgdesc="MonetDB version $pkgver"
arch=('i686' 'x86_64')
url="http://www.monetdb.org/Home"
license=('custom')
makedepends=('python' 'apache-ant' 'r-lang')
source=("http://dev.monetdb.org/downloads/sources/Latest/MonetDB-$pkgver.tar.bz2")
sha1sums=("b48ba1798600833e4ef746081ce21680136dc579")

build() {
  cd "$srcdir/MonetDB-$pkgver"
 # export RHOME=/usr/lib64/R
  ./configure --libdir=/usr/lib64 --prefix=/usr --sysconfdir=/etc --localstatedir=/var --disable-assert \
      --disable-testing --enable-optimize --enable-rintegration
 make
}

package() {
  cd "$srcdir/MonetDB-$pkgver"
  make "DESTDIR=$pkgdir" install
}

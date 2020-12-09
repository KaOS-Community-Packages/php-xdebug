pkgname=php-xdebug
pkgver=3.0.1
pkgrel=1
pkgdesc="PHP debugging extension"
arch=('x86_64')
url="http://www.xdebug.org"
license=('custom:xdebug')
depends=('php')
backup=('etc/php/conf.d/xdebug.ini')
source=(http://www.xdebug.org/files/xdebug-$pkgver.tgz
	xdebug.ini)
md5sums=('52891d89de6829fa8dba1132b8c66f75'
         'f71eeb644522ae7f1e968961896d73e1')

build() {
  cd $srcdir/xdebug-$pkgver
  phpize
  ./configure --prefix=/usr
  make
}

package() {
  cd $srcdir/xdebug-$pkgver
  make INSTALL_ROOT=$pkgdir install

  install -D -m 644 $srcdir/xdebug.ini $pkgdir/etc/php/conf.d/xdebug.ini
  install -D -m 644 $srcdir/xdebug-$pkgver/LICENSE $pkgdir/usr/share/licenses/$pkgname/LICENSE
}

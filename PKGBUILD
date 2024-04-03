pkgname=php-xdebug
pkgver=3.3.1
pkgrel=1
pkgdesc="PHP debugging extension"
arch=('x86_64')
url="http://www.xdebug.org"
license=('custom:xdebug')
depends=('php')
backup=('etc/php/conf.d/xdebug.ini')
source=(http://www.xdebug.org/files/xdebug-$pkgver.tgz
	xdebug.ini)
md5sums=('e279224d363bb95eab0d3775fae0a08f'
         '0174f042288da1ae3bca1366ccd3ed90')

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

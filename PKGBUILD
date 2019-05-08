pkgname=php-xdebug
pkgver=2.7.2
pkgrel=1
pkgdesc="PHP debugging extension"
arch=('x86_64')
url="http://www.xdebug.org"
license=('custom:xdebug')
depends=('php')
backup=('etc/php/conf.d/xdebug.ini')
source=(http://www.xdebug.org/files/xdebug-$pkgver.tgz
	xdebug.ini)
md5sums=('5d1a8ca3101df93938d283933f256493'
         '3d3cba1ae140637c1ad37fa19e310204')
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

pkgname=php-xdebug
pkgver=2.3.3
pkgrel=1
pkgdesc="PHP debugging extension"
arch=('x86_64')
url="http://www.xdebug.org"
license=('custom:xdebug')
depends=('php')
backup=('etc/php/conf.d/xdebug.ini')
source=(http://www.xdebug.org/files/xdebug-$pkgver.tgz
	xdebug.ini)
md5sums=('60e6fdf41840104a23debe16db15a2af'
         '76ae775386e0c0f9866124bec7cd9d19')

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

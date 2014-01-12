# Maintainer: George Gibbs <vash63@gmail.com>

pkgname=ds4drv
pkgver=40
pkgrel=1
pkgdesc="Sony Dual Shock 4 Bluetooth Driver"
arch=('any')
url="https://github.com/chrippa/ds4drv"
license=('MIT')
depends=('python-setuptools' 'bluez-utils')
makedepends=('perl' 'git')
install=ds4drv.install
source=("${pkgname%-*}::git+https://github.com/chrippa/ds4drv.git" 'ds4drv.tar.gz')
sha256sums=('SKIP'
            '9cf74eed8948677337ae723154e126d8c42619db9925c7dfd478671455bd5ec0')

pkgver() {
  cd "${srcdir}"/${pkgname%-*}

  git rev-list --count HEAD
}

package() { 
	cd "$srcdir/$pkgname"
	python setup.py install --root="$pkgdir/" --optimize=1
	mkdir -pm755 $pkgdir/etc/udev/rules.d
	mv $srcdir/scripts/50-uinput.rules $pkgdir/etc/udev/rules.d/50-uinput.rules
}

# vim: ft=sh syn=sh

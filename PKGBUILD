# Maintainer: George Gibbs <vash63@gmail.com>

pkgname=ds4drv
pkgver=39
pkgrel=1
pkgdesc="Sony Dual Shock 4 Bluetooth Driver"
arch=('any')
url="https://github.com/chrippa/ds4drv"
license=('MIT')
depends=('python-setuptools' 'bluez-utils')
makedepends=('perl' 'git')
source=("${pkgname%-*}::git+https://github.com/chrippa/ds4drv.git")
sha256sums=('SKIP')

pkgver() {
  cd "${srcdir}"/${pkgname%-*}

  git rev-list --count HEAD
}

package() { 
	cd "$srcdir/$pkgname"
	python setup.py install --root="$pkgdir/" --optimize=1
	mkdir -pm755 $pkgdir/etc/udev/rules.d
	mv 50-uinput.rules $pkgdir/etc/udev/rules.d/50-uinput.rules
}

# vim: ft=sh syn=sh

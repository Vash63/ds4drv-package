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
source=("${pkgname%-*}::git+https://github.com/chrippa/ds4drv.git" 'ds4drv.tar.gz')
sha256sums=('SKIP'
            '7a8a980321054b4bc233f9871356e3d49824447b6890d6cdf0f345ae9acfc9bc')

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

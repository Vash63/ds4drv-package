# Maintainer: George Gibbs <vash63 at gmail dot com>

pkgname=ds4drv
pkgver=0.3.0
pkgrel=1
pkgdesc="Sony DualShock 4 Userspace Driver"
arch=('any')
url="https://github.com/chrippa/ds4drv"
license=('MIT')
depends=('python-setuptools' 'bluez-utils' 'python-evdev' 'python-pyudev')
makedepends=('git')
conflicts=('ds4drv-git')
install=ds4drv.install
source=(https://github.com/chrippa/ds4drv/archive/v$pkgver.tar.gz)
sha256sums=('d2c5ffecf00970e2c516920bf007656aa75e6ceb01ef3ff97f9b32c032bfc636')

package() { 
	cd "$srcdir/$pkgname-$pkgver"
	mkdir -pm755 $pkgdir/etc/udev/rules.d
        cp udev/50-ds4drv.rules $pkgdir/etc/udev/rules.d/50-ds4drv.rules
	mkdir -pm755 $pkgdir/usr/share/licenses/$pkgname
	cp LICENSE $pkgdir/usr/share/licenses/$pkgname/
	python setup.py install --root="$pkgdir/" --optimize=1
	mkdir -pm755 $pkgdir/etc/systemd/system
	cp systemd/ds4drv.service $pkgdir/etc/systemd/system/ds4drv.service
	cp ds4drv.conf $pkgdir/etc/ds4drv.conf
}

# vim: ft=sh syn=sh

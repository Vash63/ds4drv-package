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
source=(https://github.com/chrippa/ds4drv/archive/v0.2.1.tar.gz 50-uinput.rules)
sha256sums=('1df6afdbfac38ef6794073a18425e32183c9a33e0a9d2447216827d0f3fc9693'
            'b67455c70a2559fbb6872949974c79503f9005ec44fd99ea2ca1f8ae47fe4d09')

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

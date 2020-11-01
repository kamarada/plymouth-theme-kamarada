# Maintainer: Matti Hyttinen  <matti@manjaro.org>

pkgname=plymouth-theme-manjaro
pkgver=2.1
pkgrel=1
pkgdesc="Plymouth theme for Manjaro"
arch=('any')
url="https://gitlab.manjaro.org/plymouth-themes/plymouth-manjaro"
license=('GPL')
depends=('plymouth')
install=plymouth.install
makedepends=('git')
source=("git+$url.git")
md5sums=('SKIP')

package() {
	cd $srcdir/$repo
	install -dm755 "$pkgdir/usr/share/plymouth/themes/manjaro"
	cp ./* "$pkgdir/usr/share/plymouth/themes/manjaro"
}

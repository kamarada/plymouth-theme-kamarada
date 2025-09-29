# Maintainer: Antonio Medeiros <linuxkamarada@gmail.com>
# Contributor: Mark Wagie <mark at manjaro dot org>
# Contributor: Matti Hyttinen  <matti@manjaro.org>

pkgname=plymouth-theme-kamarada
pkgver=1.0
pkgrel=1
pkgdesc="Plymouth theme for Kamarada"
arch=('any')
url="https://github.com/kamarada/plymouth-theme-kamarada"
license=('GPL')
depends=('plymouth')
makedepends=('plymouth' 'sed')
install='plymouth.install'
source=('watermark.png')
sha256sums=('25c68aaf803101d94f1d08ffb432d3c2072b8cad6a60da25b772fdd3bce4b7de')

package() {
  install -d "$pkgdir/usr/share/plymouth/themes"
  cp -r "/usr/share/plymouth/themes/spinner" "$pkgdir/usr/share/plymouth/themes/kamarada"
  rm "$pkgdir/usr/share/plymouth/themes/kamarada/"{spinner.plymouth,watermark.png}
  install -Dm644 "watermark.png" "$pkgdir/usr/share/plymouth/themes/kamarada/"
  cp "/usr/share/plymouth/themes/bgrt/bgrt.plymouth" "$pkgdir/usr/share/plymouth/themes/kamarada/kamarada.plymouth"
  sed -i 's/spinner/kamarada/g' "$pkgdir/usr/share/plymouth/themes/kamarada/kamarada.plymouth"
}

# Maintainer: Antonio Medeiros <linuxkamarada@gmail.com>
# Contributor: Mark Wagie <mark at manjaro dot org>
# Contributor: Matti Hyttinen  <matti@manjaro.org>

pkgname=plymouth-theme-kamarada
pkgver=20250930
pkgrel=2
pkgdesc="Plymouth theme for Kamarada"
arch=('any')
url="https://github.com/kamarada/plymouth-theme-kamarada"
license=('GPL')
depends=('plymouth' 'kamarada-distribution-logos')
makedepends=('plymouth' 'sed')
install='plymouth.install'

package() {
    install -d "$pkgdir/usr/share/plymouth/themes"
    cp -r "/usr/share/plymouth/themes/spinner" "$pkgdir/usr/share/plymouth/themes/kamarada"
    rm "$pkgdir/usr/share/plymouth/themes/kamarada/"{spinner.plymouth,watermark.png}
    ln -s /usr/share/pixmaps/kamarada-logo-text.png "$pkgdir/usr/share/plymouth/themes/kamarada/watermark.png"
    cp "/usr/share/plymouth/themes/bgrt/bgrt.plymouth" "$pkgdir/usr/share/plymouth/themes/kamarada/kamarada.plymouth"
    sed -i 's/spinner/kamarada/g' "$pkgdir/usr/share/plymouth/themes/kamarada/kamarada.plymouth"

    # We need this image to be copied to the initial ramdisk
    install -d "$pkgdir/etc/mkinitcpio.conf.d"
    echo 'FILES=(/usr/share/pixmaps/kamarada-logo-text.png)' > "$pkgdir/etc/mkinitcpio.conf.d/kamarada-logo-text.conf"
    chmod 644 "$pkgdir/etc/mkinitcpio.conf.d/kamarada-logo-text.conf"
}

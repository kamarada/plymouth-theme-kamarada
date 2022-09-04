# Maintainer: Matti Hyttinen  <matti@manjaro.org>

pkgname=plymouth-theme-manjaro
pkgver=2.2
pkgrel=1
pkgdesc="Plymouth theme for Manjaro"
arch=('any')
url="https://gitlab.manjaro.org/plymouth-themes/plymouth-manjaro"
license=('GPL')
depends=('plymouth')
makedepends=('git')
install='plymouth.install'
_commit=b8d9b1bf79849907283dac14b51b283c88caca94
source=("git+https://gitlab.manjaro.org/plymouth-themes/plymouth-manjaro.git#commit=${_commit}"
        'https://gitlab.manjaro.org/plymouth-themes/plymouth-manjaro/-/merge_requests/2.patch')
sha256sums=('SKIP'
            '986207490717a29249e0dbfc540d313599d75210cf6bec36c5cbe105da1212c0')

prepare() {
  cd "$srcdir/plymouth-manjaro"

  # New branding
  git apply -p1 < ../2.patch
}

package() {
  cd "$srcdir/plymouth-manjaro"
  install -d "$pkgdir/usr/share/plymouth/themes"
  cp -r manjaro "$pkgdir/usr/share/plymouth/themes/"
}

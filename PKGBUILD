# Maintainer: Georg Wagner <puxplaying_at_gmail_dot_com>
# Contributor: Hanzel <https://github.com/HanzelM>
# Contributor: Jazz <https://github.com/jazz-it>

pkgname=maus
pkgver=1.5
pkgrel=1
pkgdesc="Bash script to update and maintain a Manjaro or Arch system"
arch=(any)
url="https://github.com/puxplaying/manjaro-update"
license=('GPL-3.0-or-later')
depends=(
  'bash'
  'pacman'
  'pacman-contrib'
  'sudo'
)
makedepends=('git')
optdepends=(
  'meld: Needed for diff operations'
  'reflector: Needed for Arch mirrorlist update'
)
conflicts=(manjaro-update)
source=("$pkgname-$pkgver.tar.gz::$url/archive/$pkgver.tar.gz")
sha256sums=('f0dddb3cc0c6b14b82ffd46a6b2864a8328c6181f9b675feaf32c1e2b480e8b7')

package() {
	cd "$srcdir/$pkgname-$pkgver"
	install -Dm644 "update.desktop" "$pkgdir/usr/share/applications/update.desktop"
	install -Dm644 "update.png" "$pkgdir/usr/share/pixmaps/update.png"
	install -Dm755 "$srcdir/$pkgname-$pkgver/$pkgname" "$pkgdir/usr/bin/$pkgname"
}

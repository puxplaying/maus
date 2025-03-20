# Maintainer: Georg Wagner <puxplaying_at_gmail_dot_com>
# Contributor: Hanzel <https://github.com/HanzelM>

pkgname=maus
pkgver=1.3
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
sha256sums=('ed252ebdf70b90c4f4323ed3f75adf3ae6f4ae96f563b95b6a9298c343e98580')

package() {
	cd "$srcdir/$pkgname-$pkgver"
	install -Dm644 "update.desktop" "$pkgdir/usr/share/applications/update.desktop"
	install -Dm644 "update.png" "$pkgdir/usr/share/pixmaps/update.png"
	install -Dm755 "$srcdir/$pkgname-$pkgver/$pkgname" "$pkgdir/usr/bin/$pkgname"
}

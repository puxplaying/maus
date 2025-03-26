# Maintainer: Georg Wagner <puxplaying_at_gmail_dot_com>
# Contributor: Hanzel <https://github.com/HanzelM>
# Contributor: Jazz <https://github.com/jazz-it>

pkgname=maus
pkgver=1.4
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
sha256sums=('7ad670a0427886f12897307875259fa55b8df28a38d9e415d2034c81cda6e4f7')

package() {
	cd "$srcdir/$pkgname-$pkgver"
	install -Dm644 "update.desktop" "$pkgdir/usr/share/applications/update.desktop"
	install -Dm644 "update.png" "$pkgdir/usr/share/pixmaps/update.png"
	install -Dm755 "$srcdir/$pkgname-$pkgver/$pkgname" "$pkgdir/usr/bin/$pkgname"
}

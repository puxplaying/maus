# Maintainer: Georg Wagner <puxplaying_at_gmail_dot_com>

pkgname=maus
pkgver=1.0
pkgrel=1
pkgdesc="Bash script to update and maintain a Manjaro or Arch system"
arch=(any)
url="https://github.com/puxplaying/manjaro-update"
license=('GPL3')
depends=('pacman' 'sudo' 'bash')
makedepends=('git')
optdepends=('meld: Needed for diff operations'
	'reflector: Needed for Arch mirrorlist update')
conflicts=(manjaro-update)
source=("$pkgname-$pkgver.tar.gz::$url/archive/$pkgver.tar.gz")
sha256sums=('903d76ae484281de7d4447f1dff0374c42639736adf5f185d9f4b11bc0ad7420')

package() {
	cd "$srcdir/$pkgname-$pkgver"
	install -Dm644 "update.desktop" "$pkgdir/usr/share/applications/update.desktop"
	install -Dm644 "update.png" "$pkgdir/usr/share/pixmaps/update.png"
	install -Dm755 "$srcdir/$pkgname-$pkgver/$pkgname" "$pkgdir/usr/bin/$pkgname"
}

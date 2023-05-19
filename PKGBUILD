# Maintainer: Georg Wagner

pkgname=manjaro-update
pkgver=0.6
pkgrel=1
pkgdesc="Bash script to update and maintain a Manjaro or Arch system"
arch=(any)
url="https://github.com/puxplaying/manjaro-update"
license=('GPL3')
depends=('pacman' 'sudo' 'bash')
makedepends=('git')
optdepends=('meld: Needed for diff operations'
			'reflector: Needed for Arch mirrorlist update')
source=("$pkgname-$pkgver.tar.gz::$url/archive/$pkgver.tar.gz")
sha256sums=('f2776096079045ed640a818d4c5da3fdbe9099f5fb03d1f829ce51840cd644e1')

package () {
	cd "$srcdir/$pkgname-$pkgver"
	install -Dm644 "update.desktop" "$pkgdir/usr/share/applications/update.desktop"
	install -Dm644 "update.png" "$pkgdir/usr/share/pixmaps/update.png"
	install -Dm755 "$srcdir/$pkgname-$pkgver/manjaro-update" "$pkgdir/usr/bin/manjaro-update"
}

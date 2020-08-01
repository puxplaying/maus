# Maintainer: puxplaying

pkgname=manjaro-update
pkgver=0.1
pkgrel=1
pkgdesc="Bash script to update and maintain a Manjaro system"
arch=(any)
url="https://github.com/puxplaying/manjaro-update"
license=('GPL3')
depends=('pacman' 'sudo' 'bash')
makedepends=('git')
optdepends=('meld: Needed for diff operations')
source=("$url/archive/$pkgver.tar.gz")
md5sums=('SKIP')

package () {
	cd "$srcdir/$pkgname-$pkgver"
	install -Dm644 "update.desktop" "$pkgdir/usr/share/applications/update.desktop"
	install -Dm644 "update.png" "$pkgdir/usr/share/pixmaps/update.png"
	install -Dm755 "$srcdir/$pkgname-$pkgver/manjaro_update" "$pkgdir/usr/bin/manjaro_update"
}

# Maintainer:  lolilolicon <lolilolicon#gmail#com>
# Contributor: lolilolicon <lolilolicon#gmail#com>

pkgname=contagious
pkgver=1.0
pkgrel=1
pkgdesc="contagious boosts your download speed by pulling the target from multiple
mirrors around the world."
arch=(any)
url="http://lolilolicon.github.com/contagious"
license=('MIT')
depends=(bash aria2)
source=(https://github.com/downloads/lolilolicon/$pkgname/$pkgname-$pkgver.tar.gz)
md5sums=('3404dbc0a9797ad66785f6501e810202')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  # change profile directory path
  # sed '4s|.*|profiles_dir=${HOME}/bin/contagious.d|'
}
package() {
  cd "$srcdir/$pkgname-$pkgver"

  install -Dm 755 contagious "$pkgdir"/usr/bin/contagious

  # install sample profiles
  install -d "$pkgdir"/usr/share/${pkgname}/contagious.d/
  cp -r contagious.d/* "$pkgdir"/usr/share/${pkgname}/contagious.d/
  install -m 644 README.md "$pkgdir"/usr/share/${pkgname}/
}

# vim:set ts=2 sw=2 et:

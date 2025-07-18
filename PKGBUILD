pkgname=dome-shell-git
pkgver=0.1.3.r16.geda9ca5
pkgrel=1
pkgdesc="A familiar looking Hyprland shell"
arch=("x86_64")
url="https://github.com/deorbil/dome-shell"
license=("GPL-3.0-only")
depends=("aylurs-gtk-shell")
makedepends=("git" "npm")
provides=("dome-shell")
conflicts=("dome-shell")
source=("git+https://github.com/deorbil/dome-shell.git")
sha256sums=("SKIP")

pkgver() {
  cd "$srcdir/dome-shell"
  git describe --long | sed "s/^v//;s/\([^-]*-g\)/r\1/;s/-/./g"
}

build() {
  cd "$srcdir/dome-shell"
  npm run build
}

package() {
  cd "$srcdir/dome-shell"
  install -Dm755 "dist/dome-shell" "$pkgdir/usr/bin/dome-shell"
  install -Dm644 "LICENSE" "$pkgdir/usr/share/licenses/dome-shell/LICENSE"
  install -Dm644 "README.md" "$pkgdir/usr/share/doc/dome-shell/README.md"
}

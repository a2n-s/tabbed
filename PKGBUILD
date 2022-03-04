# Maintainer: Antoine Stevan
pkgname=tabbed-a2ns-git
pkgver=5.0.r628.7e63f07
pkgrel=1
epoch=
pkgdesc="A patched build of tabbed."
arch=(x86_64)
url="https://github.com/a2n-s/tabbed.git"
license=('GNU')
groups=()
depends=()
makedepends=(git)
checkdepends=()
optdepends=()
provides=(tabbed)
conflicts=(tabbed)
replaces=()
backup=()
options=()
install=
changelog=
source=("git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()

pkgver() {
  cd "${_pkgname}"
  printf "5.0.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd tabbed
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  cd tabbed
  mkdir -p ${pkgdir}/opt/${pkgname}
  cp -rf * ${pkgdir}/opt/${pkgname}
  make PREFIX=/usr DESTDIR="${pkgdir}" install
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  install -Dm644 README.md "${pkgdir}/usr/share/doc/${pkgname}/README.md"
}

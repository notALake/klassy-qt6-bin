pkgname=klassy
pkgver=__PKGVER__
pkgrel=1
pkgdesc='Highly customizable binary Window Decoration, Application Style and Global Theme plugin for recent versions of the KDE Plasma desktop (Qt6 only).'
arch=(x86_64)
url="https://github.com/paulmcauley/klassy"
license=('GPL-2.0-only AND GPL-3.0-only AND GPL-2.0-or-later AND LGPL-2.1-or-later AND MIT')
replaces=(classik)
depends=(breeze-icons
         hicolor-icon-theme
         frameworkintegration
         gcc-libs
         glibc
         kcmutils
         kcolorscheme
         kconfig
         kcoreaddons
         kdecoration
         kguiaddons
         ki18n
         kiconthemes
         kwidgetsaddons
         kwindowsystem
         qt6-base
         qt6-declarative
         qt6-svg
         xdg-utils)
makedepends=(extra-cmake-modules)
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/refs/tags/v${pkgver}.tar.gz")
sha256sums=('SKIP')

build() {
  cmake -B build -S "${pkgname}-${pkgver}" \
    -DBUILD_TESTING=OFF \
    -DBUILD_QT5=OFF
  cmake --build build
}

package() {
  DESTDIR="${pkgdir}" cmake --install build
  install -Dm644 "${pkgname}-${pkgver}/LICENSES/MIT.txt" "${pkgdir}/usr/share/licenses/${pkgname}/MIT.txt"
}

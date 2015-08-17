 
# Maintainer: Dany Martineau <dany.luc.martineau at gmail.com>

pkgname=qt5ct-svn
_pkgname=qt5ct
pkgver=r139
pkgrel=1
pkgdesc="Qt5 Configuration Tool - svn version."
arch=('i686' 'x86_64')
url="http://qt-apps.org/content/show.php/Qt5+Configuration+Tool?content=168066"
license=('BSD')
depends=('qt5-base')
makedepends=('subversion' 'cmake' 'qt5-tools')
conflicts=('qt5ct')
provides=('qt5ct')
source=("$_pkgname::svn+https://svn.code.sf.net/p/qt5ct/code/trunk")
install=qt5ct.install
sha1sums=('SKIP')


build() {
  cd "${srcdir}/${_pkgname}/${_pkgname}"
  qmake
  make
}

package() {
  cd "${srcdir}/${_pkgname}/${_pkgname}/src/qt5ct-qtplugin"

  install -Dm 755 -p "libqt5ct.so" "${pkgdir}/usr/lib/qt/plugins/platformthemes/libqt5ct.so"
  cd "../qt5ct"
  install -Dm 755 -p "qt5ct" "${pkgdir}/usr/lib/qt/bin/qt5ct"
  mkdir "${pkgdir}/usr/bin"
  ln -sr "${pkgdir}/usr/lib/qt/bin/qt5ct" "${pkgdir}/usr/bin/qt5ct"
  install -Dm 644 -p "qt5ct.desktop" "${pkgdir}/usr/share/applications/qt5ct.desktop"
}
# Maintainer: Antonio Rojas 

pkgname=kaccounts-providers-frameworks-git
pkgver=r33.8b96be7
pkgrel=1
pkgdesc='Small system to administer web accounts for the sites and services across the KDE desktop, including: Google, Facebook, Owncloud, IMAP, 
Jabber and others'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/playground/base/kde-accounts/kaccounts-providers'
license=('GPL')
depends=('libaccounts-glib')
makedepends=('extra-cmake-modules' 'git')
source=("git://anongit.kde.org/kaccounts-providers.git#branch=frameworks")
sha256sums=('SKIP')

pkgver() {
  cd kaccounts-providers
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../kaccounts-providers \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_BUILD_TYPE=Release
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}

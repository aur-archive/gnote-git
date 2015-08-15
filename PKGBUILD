# Contributor: Andre Klitzing  <aklitzing () online () de>
# Contributor: josephgbr <rafael.f.f1@gmail.com>

_name=gnote
pkgname=$_name-git
pkgver=3.13.0
pkgrel=1
pkgdesc="A note taking application"
arch=('i686' 'x86_64')
url="http://live.gnome.org/Gnote"
license=('GPL')
depends=('gtkmm3' 'gtkspell3' 'libxslt' 'libsecret' 'desktop-file-utils' 'yelp-tools'  'hicolor-icon-theme' 'boost' 'gnome-common' 'intltool' 'git')
provides=("$_name")
conflicts=("$_name")
options=('!libtool')
install=$_name.install
source=("git://git.gnome.org/$_name")
md5sums=('SKIP')

pkgver() {
  cd $_name
  git describe --tags | sed -e 's/-/./g'
}

build() {
  cd $_name
  ./autogen.sh --prefix=/usr --disable-schemas-compile
  make
}

package() {
  cd $_name
  make DESTDIR="$pkgdir" install
}


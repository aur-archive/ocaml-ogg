# Maintainer: Charles E. Hawkins <charlesthehawk at yahoo dot com>
# Contributor: Thomas S Hatch <thatch45 at gmail dot com>
# Contributor: Luciano A. Ferrer <laferrer@gmail.com>
pkgname=ocaml-ogg
pkgver=0.4.5
pkgrel=1
arch=('i686' 'x86_64')
license=('GPL')
pkgdesc="OCaml bindings for the Ogg bitstream library."
url="http://savonet.sourceforge.net/"
depends=('libogg')
makedepends=('ocaml' 'ocaml-findlib')
options=('!strip')
source=("http://downloads.sourceforge.net/savonet/${pkgname}-${pkgver}.tar.gz")
md5sums=('9886cda77b15c38343449d2e13a5c8a9')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./configure --prefix=/usr
  make all
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  mkdir -p ${pkgdir}$(ocamlfind printconf destdir)
  make \
    OCAMLFIND_DESTDIR=${pkgdir}$(ocamlfind printconf destdir) \
    OCAMLFIND_LDCONF=ignore \
    install
}

# Maintainer: Tom Swartz <tom@tswartz.net>

pkgname=catimg
_pkgname=catimg
pkgver=1
pkgrel=1
pkgdesc="Insanely fast image printing in your terminal. Latest commit from Github."
arch=('any')
url="https://github.com/posva/${_pkgname}"
license=('MIT')
depends=('imagemagick')
makedepends=('git')
source=(${_pkgname}::"git+https://github.com/posva/${_pkgname}.git")
sha256sums=('SKIP')
conflicts=('')

pkgver() {
        cd "${srcdir}/${_pkgname}"
        echo "$(git rev-list --count HEAD).$(git rev-parse --short HEAD)"
}

build() {
        cd "${srcdir}/${_pkgname}"
        cmake .
}

package() {
        make -C "${srcdir}/${_pkgname}" DESTDIR="${pkgdir}" install
}


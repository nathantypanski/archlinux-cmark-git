# Maintainer: Nathan Typanski <mail@nathantypanski.com>

_pkgname=commonmark
pkgname="$_pkgname"-git
pkgver=r56.e92aabb
pkgrel=1
pkgdesc="cmark CommonMark compiler"
arch=('i686' 'x86_64')
url="https://github.com/jgm/CommonMark.git"
license=('BSD3')
depends=('re2c')
options=(!emptydirs libtool)
source=(git://github.com/jgm/$_pkgname.git)

pkgver() {
        cd "$pkgname"
        printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
        cd "${srcdir}/${_pkgname}"
        make
        gzip man/man1/cmark.1
}

check() {
        cd "${srcdir}/${_pkgname}"
        make test
}

package() {
        cd "${srcdir}/${_pkgname}"
        install -Dm755 stmd "$pkgdir/usr/bin/stmd"
        install -Dm644 man/man1/cmark.1.gz "$pkgdir/usr/share/man/man1/cmark.1.gz"
}

md5sums=('SKIP'
)
sha256sums=('SKIP'
)

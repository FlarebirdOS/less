pkgname=less
pkgver=679
pkgrel=2
pkgdesc="A terminal based program for viewing text files"
arch=('x86_64')
url="https://www.greenwoodsoftware.com/less/"
license=(
    'GPL-3.0-or-later'
    'BSD-2-Clause'
)
depends=(
    'glibc'
    'ncurses'
    'pcre2'
)
source=(https://www.greenwoodsoftware.com/${pkgname}/${pkgname}-${pkgver}.tar.gz)
sha256sums=(9b68820c34fa8a0af6b0e01b74f0298bcdd40a0489c61649b47058908a153d78)

build() {
    cd ${pkgname}-${pkgver}

    local configure_args=(
        --sysconfdir=/etc
        --with-regex=pcre2
        ${configure_options}
    )

    ./configure "${configure_args[@]}"

    make
}

package() {
    cd ${pkgname}-${pkgver}

    make DESTDIR=${pkgdir} install
}

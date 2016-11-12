# Maintainer: Christian Wieden <wiedenchr at gmail dot com
# Contributor: Ricardo Band <me at xengi dot de>
# Contributor: Filip Szymański <fszymanski at, fedoraproject.org>

pkgname=hstr
pkgver=1.21
pkgrel=1
pkgdesc="A command line utility that brings improved BASH command completion from the history. It aims to make completion easier and more efficient than Ctrl-r."
arch=('any')
url="https://github.com/dvorka/hstr"
license=('Apache')
makedepends=('autoconf' 'automake' 'ncurses' 'readline')
source=(${pkgname}-${pkgver}.tar.gz::https://github.com/dvorka/${pkgname}/archive/${pkgver}.tar.gz)
sha256sums=('f0e9762f2a9587f0995bbd51cb64526ae852c2425ceb8ceee0747efba80ac6b3')

prepare() {
    cd "${pkgname}-${pkgver}"
    sed -i -e "s#<ncursesw/curses.h>#<curses.h>#g" src/include/hstr_curses.h
    sed -i -e "s#<ncursesw/curses.h>#<curses.h>#g" src/hstr.c
}

build() {
    cd "${pkgname}-${pkgver}/dist"
    ./1-dist.sh
    cd ..
    ./configure --prefix=/usr
    make
}

package() {
    cd "${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}/" install
    install -D -p -m 644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
    install -D -p -m 644 Changelog "${pkgdir}/usr/share/doc/${pkgname}/Changelog"
    install -D -p -m 644 README.md "${pkgdir}/usr/share/doc/${pkgname}/README.md"
}

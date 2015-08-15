# Maintainer: James Cleveland <jamescleveland at gmail dot com>

pkgname=dmenu-dogs
pkgver=4.5
pkgrel=4
pkgdesc="dmenu is a dynamic menu for X, originally designed for dwm. It manages large numbers of user-defined menu items efficiently (Dogs colourscheme)"
url="http://tools.suckless.org/dmenu/"
depends=('terminus-font')
conflicts=('dmenu')
provides=('dmenu')
license=('MIT')
arch=('any')
source=("http://dl.suckless.org/tools/dmenu-4.5.tar.gz" "dogs-theme.patch" "text-align.patch")
md5sums=('9c46169ed703732ec52ed946c27d84b4' '96735bac6887ce30c5756efd8ba6b11f' 'a8b54d6db401824b47fba0d46e9fac43')

build() {
    cd $srcdir/dmenu-$pkgver
    patch dmenu.c ../dogs-theme.patch
    patch draw.c ../text-align.patch
    make 
}   

package() {
    cd $srcdir/dmenu-$pkgver
    make DESTDIR=$pkgdir PREFIX=/usr install 
    install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}

# vim:set ts=2 sw=2 et:

# Maintainer: Felix Yan <felixonmars@gmail.com>
# Contributor: Andrzej Giniewicz <gginiu@gmail.com>

pkgname=python2-ets-doc
pkgver=4.4.1
pkgrel=1
pkgdesc="Documentation for ETS"
arch=('any')
url="https://github.com/enthought/ets"
license=('BSD')
depends=('python2-apptools-doc' 'python2-blockcanvas-doc' 'python2-chaco-doc'
         'python2-codetools-doc' 'python2-enable-doc' 'python2-envisage-doc'
         'python2-etsdevtools-doc' 'python2-mayavi-doc' 'python2-pyface-doc'
         'python2-scimath-doc' 'python2-traits-doc' 'python2-traitsui-doc')
makedepends=('python2-sphinx' "python2-ets=$pkgver")
conflicts=('python2-ets-doc-git')
options=(!emptydirs)
source=("https://github.com/enthought/ets/archive/${pkgver}.tar.gz")

build() {
  cd "$srcdir/ets-$pkgver/docs"
  make SPHINXBUILD=sphinx-build2 html
}

package() {
  cd "$srcdir/ets-$pkgver/docs"
  install -d "${pkgdir}"/usr/share/doc/enthought/ets
  cp -r build/html/* "${pkgdir}"/usr/share/doc/enthought/ets

  install -Dm644 "../LICENSE.txt" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

sha512sums=('5e95485699405b1f6fa9288b1db05ad398496b5d7ea4265213f7299ac64ad171c29344e8126539642dc82860bd63493f3e13fb942e7347a28a75af4f2832251b')

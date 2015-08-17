# Maintainer: Alexander Rødseth <rodseth@gmail.com>

pkgname=poclbm
pkgver=10.12
pkgrel=1
pkgdesc='PyOpenCL bitcoin miner'
url='https://github.com/m0mchil/poclbm'
arch=('x86_64' 'i686')
license=('public domain')
depends=('python2' 'python2-pyopencl' 'python2-pyserial' 'python2-numpy')
source=("$pkgname.tgz::https://github.com/m0mchil/poclbm/archive/master.tar.gz"
        'poclbm.sh')
sha256sums=('7e75e03e51036af01f558c8d5d43a04e6062e6a5c310b5064798dc01e820c9fd'
            'da1cb0f2520882fb6a4af2209fabf06008359712e5d04812d2c77c697601c9f0')
         
build() {
  chmod -x "$srcdir/$pkgname-master/"*
}

package() {
  cd "$srcdir"

  #python2 setup.py install --root=$pkgdir --optimize=1

  mkdir -p "$pkgdir/opt"
  cp -r "$srcdir/$pkgname-master" "$pkgdir/opt/$pkgname"
  install -Dm755 poclbm.sh "$pkgdir/usr/bin/$pkgname"
  install -Dm644 "$srcdir/$pkgname-master/LICENSE" \
    "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

# vim:set ts=2 sw=2 et:

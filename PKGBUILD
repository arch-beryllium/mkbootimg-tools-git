_pkgname=mkbootimg
pkgname=$_pkgname-tools-git
pkgver=r331.8d0922b
pkgrel=1
pkgdesc='mkbootimg tools'
arch=(any)
url='https://android.googlesource.com/platform/system/tools/mkbootimg'
license=(Apache MIT)
depends=(python python2)
provides=($_pkgname-tools)
source=(git+https://android.googlesource.com/platform/system/tools/mkbootimg)
sha1sums=('SKIP')

pkgver() {
  cd $_pkgname
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd "$srcdir"/mkbootimg
  sed -i 's|/usr/bin/env python$|/usr/bin/env python2|g' unpack_bootimg.py
}

package() {
  install -m755 -d "$pkgdir"/usr/bin
  install -Dm 755 mkbootimg/mkbootimg.py "$pkgdir"/usr/bin/mkbootimg
  install -Dm 755 mkbootimg/unpack_bootimg.py "$pkgdir"/usr/bin/unpack_bootimg
}

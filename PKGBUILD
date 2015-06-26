pkgname=roswell
pkgrel=1
pkgdesc="Common Lisp environment setup Utility."

arch=('i686' 'x86_64')
url="https://github.com/snmsts/roswell"
license="MIT"

source=('roswell::git+https://github.com/snmsts/roswell.git#branch=release')
pkgver() {
  cd $srcdir/$pkgname
  git describe --long | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

depends=('curl' 'automake' 'autoconf')

build () {
  cd $srcdir/$pkgname

  sh bootstrap
  ./configure --prefix=/usr
  make 
}

package () {
  cd $srcdir/$pkgname
  make DESTDIR="$pkgdir" install
}

md5sums=('SKIP')

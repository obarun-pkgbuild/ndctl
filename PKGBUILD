# Maintainer: Eric Vidal <eric@obarun.org>
# based on the original https://git.archlinux.org/svntogit/packages.git/log/trunk?h=packages/ndctl

pkgname=ndctl
pkgver=60.3
pkgrel=2
pkgdesc='Utility library for managing the libnvdimm (non-volatile memory device) sub-system in the Linux kernel'
arch=('x86_64')
url="https://github.com/pmem/ndctl"
license=('LGPL')
depends=('json-c' 'kmod' 'eudev-obarun' 'libutil-linux')
makedepends=('asciidoc' 'xmlto' 'bash-completion')
source=("$pkgname-$pkgver.tar.gz::https://github.com/pmem/ndctl/archive/v$pkgver.tar.gz")
sha512sums=('59f2fecec95a268258501b996a8343149a96e12e3825d327e20aa2f2c92299e31c3b8063df16922f2ea26a3c2a68ce21b4ab55a42298840804d0d4eb9a15041b')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

build() {
  cd "$srcdir"/$pkgname-$pkgver
  ./autogen.sh
  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir"/$pkgname-$pkgver
  make DESTDIR="$pkgdir" install
}

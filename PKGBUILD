# Maintainer:  <dev@quorumcontrol.com>
pkgname=dgit
pkgver="v0.0.15_alpha"
pkgrel=1
pkgdesc="Decentralized git remotes"
arch=('x86_64')
url="https://dgit.dev"
license=('MIT')
depends=(
  "git"
)
source=("https://github.com/quorumcontrol/$pkgname/releases/download/${pkgver//_/-}/$pkgname-Linux-$arch.tar.gz")
sha256sums=('c57d1416c8841d6cf198f375da57962e5c0ece81d087d1e6a537e67ae98d8ad9')

package() {
  cd "$srcdir/"
  bindir="$pkgdir/usr/bin/"
  mkdir -p $bindir
  cp dgit $bindir
  cp git-remote-dgit $bindir
}

# vim:set ts=2 sw=2 et:

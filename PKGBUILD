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
makedepends=(
  "go"
)
source=("https://github.com/quorumcontrol/$pkgname/archive/${pkgver//_/-}.tar.gz")
sha256sums=("59558367e31a92f4b9fb77d2f9570c241fda3d8b1f1a8b5133b1c376b24d4587")

package() {
  cd "$srcdir/"
  bindir="$pkgdir/usr/bin/"
  mkdir -p $bindir
  cp dgit $bindir
  cp git-remote-dgit $bindir
}

# vim:set ts=2 sw=2 et:

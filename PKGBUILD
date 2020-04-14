# Maintainer:  <dev@quorumcontrol.com>
pkgname=dgit
pkgver="v0.0.15-alpha"
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
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/quorumcontrol/$pkgname/archive/$pkgver.tar.gz")
sha256sums=("59558367e31a92f4b9fb77d2f9570c241fda3d8b1f1a8b5133b1c376b24d4587")

build() {
  export GOPATH="$srcdir"/gopath
  cd "$srcdir/$pkgname-$pkgver"
  EXTRA_GOFLAGS="-modcacherw -gcflags all=-trimpath=${PWD} -asmflags all=-trimpath=${PWD}" \
    LDFLAGS="-linkmode external -extldflags \"${LDFLAGS}\"" \
    make VERSION="$pkgver" DESTDIR="$pkgdir" PREFIX="/usr" build
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make VERSION="$pkgver" DESTDIR="$pkgdir" PREFIX="/usr" install
}

# vim:set ts=2 sw=2 et:

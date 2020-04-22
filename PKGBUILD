# Maintainer:  <dev@quorumcontrol.com>
pkgname="decentragit"
pkgver="v0.0.15_alpha"
pkgrel=1
pkgdesc="Decentralized git remotes"
arch=('x86_64')
url="https://dgit.dev"
license=('MIT')
provides=('git-dg')
depends=(
  "git"
)
makedepends=(
  "go"
)
source=("${pkgname}-${pkgver//_/-}.tar.gz::https://github.com/quorumcontrol/$pkgname/archive/${pkgver//_/-}.tar.gz")
sha256sums=("59558367e31a92f4b9fb77d2f9570c241fda3d8b1f1a8b5133b1c376b24d4587")

build() {
  export GOPATH="$srcdir"/gopath
  cd "$srcdir/$pkgname-${pkgver//_/-}"
  EXTRA_GOFLAGS="-modcacherw -gcflags all=-trimpath=${PWD} -asmflags all=-trimpath=${PWD}" \
    LDFLAGS="-linkmode external -extldflags \"${LDFLAGS}\"" \
    make VERSION=${pkgver//_/-} DESTDIR="$pkgdir" PREFIX="/usr" build
}

package() {
  cd "$srcdir/$pkgname-${pkgver//_/-}"
  make VERSION=${pkgver//_/-} DESTDIR="$pkgdir" PREFIX=/usr install
}

# vim:set ts=2 sw=2 et:

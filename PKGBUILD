# Maintainer: David K david.dk949@gmail.com
pkgname=waitd
pkgver="unknown"
pkgrel=0
pkgdesc="Run a command after a period of inactivity."
arch=('x86_64')
url="https://github.com/dk949/$pkgname"
license=('MIT')
depends=(
    'libX11.so=6'
    'libXau.so=6'
    'libXdmcp.so=6'
    'libXext.so=6'
    'libXss.so=1'
    'libxcb.so=1'
)
provides=('waitd')
source=("git+$url")
md5sums=() #autofill using updpkgsums
sha256sums=('SKIP')

pkgver() {
    git -C "$pkgname" describe | sed 's/-/_/g'
}

build() {
    cd "$pkgname"
    make
}

package() {
    cd "$pkgname"

    make DESTDIR="$pkgdir/" PREFIX="/usr" install
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

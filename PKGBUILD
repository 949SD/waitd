# Maintainer: David K david.dk949@gmail.com
pkgname=waitd
pkgver="unknown"
pkgrel=0
pkgdesc="Run a command after a period of inactivity."
arch=('x86_64')
url="https://github.com/dk949/$pkgname"
license=('MIT')
depends=(
    'libxss'   # libXss.so
    'libx11'   # libX11.so
    'libxext'  # libXext.so
    'libxcb'   # libxcb.so
    'libxau'   # libXau.so
    'libxdmcp' # libXdmcp.so
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
    make -j
}

package() {
    cd "$pkgname"

    make DESTDIR="$pkgdir/" PREFIX="/usr" install
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

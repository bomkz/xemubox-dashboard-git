pkgname=xemubox-dashboard-git
pkgver=0.0.1
pkgrel=1
pkgdesc='XemuBOX Dashboard, used by the XemuBOX as a game picker.'
arch=('x86_64')
url=https://github.com/bomkz/xemubox-dashboard
license=('MIT')
makedepends=('npm' 'nodejs')
depends=('fuse2' 'nss' 'libxss' 'libxtst' 'libxrandr' 'libxcomposite' 'libxdamage' 'libxkbcommon' 'gtk3')
source=("xemubox-dashboard::git+https://github.com/bomkz/xemubox-dashboard.git")
sha256sums=('SKIP')

prepare() {
    cd "$srcdir/xemubox-dashboard"
    mkdir -p build/
}

build() {
    cd "$srcdir/xemubox-dashboard"
    NODE_ENV=development npm install
    NODE_ENV=development npm run build:linux
}

check() {
    cd "$srcdir/xemubox-dashboard"
}

package() {
    cd "$srcdir/xemubox-dashboard"
    install -Dm755 "dist/xemubox-dashboard" "$pkgdir/usr/bin/xemubox-dashboard"
}
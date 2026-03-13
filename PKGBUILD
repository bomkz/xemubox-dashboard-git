pkgname=xemubox-dashboard-git
pkgver=0.0.1
pkgrel=1
pkgdesc='XemuBOX Dashboard, used by the XemuBOX as a game picker.'
arch=('x86_64')
url=https://github.com/bomkz/xemubox-dashboard
license=('The Unlicense')
makedepends=('npm' 'nodejs')
source=("git+https://github.com/bomkz/xemubox-dashboard.git")
sha256sums=("SKIP")
srcname=xemubox-dashboard
bin=xemubox-dashboard
NODE_ENV=development 

prepare(){
	cd "$srcname"
	mkdir -p build/
}

build(){
	cd "$srcname"
    npm install
    npm run build:linux
}


check() {
	cd "$srcname"
}

package() {
	cd "$srcname"
	install -Dm755 "dist/$srcname" "$pkgdir/usr/bin/$srcname"
}

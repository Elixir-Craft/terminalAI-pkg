# Maintainer: Nirmal Savinda <hwnsavi@gmail.com>
pkgname='terminalai'
pkgver=v0.1.0
pkgrel=1
pkgdesc="AI tool for text and code generation using Gemini and OpenAI APIs."
arch=('x86_64')
url='https://github.com/Elixir-Craft/terminalAI'
license=('MIT')
groups=()
depends=('glibc')
makedepends=('go')
source=("$pkgname::git+$url.git#tag=$pkgver")
sha256sums=('SKIP')

prepare() {
	cd "$pkgname"

	if [ ! -d build ]; then
		mkdir build
	fi


	export GOPATH="${srcdir}"
	go mod tidy
}

build() {
	cd "$pkgname"
	export GOPATH="${srcdir}"

	go build -v -o build ./...
}

# check() {
# 	cd "$pkgname"
# 	make -k check
# }

package() {
	cd "$pkgname"


	install -Dm755 build/terminalai "${pkgdir}/usr/bin/terminalai"

	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"

	install -Dm644 README.md "${pkgdir}/usr/share/doc/${pkgname}/README.md"

	
	

}

# Reference: https://postmarketos.org/devicepkg

maintainer="yewgamer <yewgame3@gmail.com>"
pkgname=device-xiaomi-apollo
pkgdesc="Xiaomi Mi 10T 5G (Apollo) – temporary combined device+DTB package"
pkgver=1
pkgrel=0
url="https://postmarketos.org"
license="MIT"
arch="aarch64"
options="!check !archcheck"

depends="
	linux-postmarketos-qcom-sm8250
	mkbootimg
	shellcheck
	postmarketos-base
"

makedepends="devicepkg-dev"

source="
	deviceinfo
	modules-initfs
	sm8250-xiaomi-apollo.dtb
"

build() {
	devicepkg_build "$startdir" "$pkgname"
}

package() {
	# normal device package stuff
	devicepkg_package "$startdir" "$pkgname"

	# install DTB directly (temporary hack, but works)
	install -Dm644 "$srcdir/sm8250-xiaomi-apollo.dtb" \
		"$pkgdir/boot/dtbs/qcom/sm8250-xiaomi-apollo.dtb"
}

sha512sums="
3b1e3fcc565279348045d05733c06b29954e779a9b54123ce0b77470e70e491029b09a8fdd316f566347738a0bfd490a02a93a612881d61fc0cbdfe7b51e1a47  deviceinfo
1f7e042f8462f169933c877b7aae6b00e0eb3718714d077891b4cd1b9c0c8aa5fb18ec0d7058ad6b7c6360560ed4e0c1c464ea9d2e35a1125dd4f8d012beecc2  modules-initfs
a5b02a1716740af76a32e43468fd46b25e73c13ce96fee38881b1e593f8703bb44a13bcbc42554a0ca1af150202ea79433761d585a2a5570882234e76af6222a  sm8250-xiaomi-apollo.dtb
"

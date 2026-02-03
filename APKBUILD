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
	mesa-vulkan-freedreno
	make-dynpart-mappings
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
d94d0deb082fa864deecc285c18883f4b0fb9399f2e2af297998628d02f01c0637bd89f62543ec7ae6ea3610625e91e41899c6852541e9873328359437a82be9  deviceinfo
e7dbb157ed314b2f62e41e102032467d2509e84686fa103ad588ac6f05b9833c80dc736e179614776f3403dc6081c74680acbc1f0fec2423dbc4509c7a96225a  modules-initfs
a5b02a1716740af76a32e43468fd46b25e73c13ce96fee38881b1e593f8703bb44a13bcbc42554a0ca1af150202ea79433761d585a2a5570882234e76af6222a  sm8250-xiaomi-apollo.dtb
"

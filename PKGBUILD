# Maintainer: ava1ar <mail(at)ava1ar(dot)info>

pkgname=chromium-libpdf
pkgdesc="Google Chrome's PDF plugin for Chromium (stable version)"
pkgver=36.0.1985.125
pkgrel=1
epoch=1
_verbld=${pkgver}-1
_channel='stable'
arch=('i686' 'x86_64')
url="http://www.google.com/chrome"
license=('custom:chrome')
depends=('chromium')
conflicts=('chromium-libpdf-dev')
install=chromium-libpdf.install
source=(license.html::http://www.google.com/chrome/intl/en/eula_text.html)
sha1sums=('SKIP')
if [ "$CARCH" == x86_64 ]; then
	source+=(https://dl.google.com/linux/chrome/rpm/stable/x86_64/google-chrome-${_channel}-${_verbld}.x86_64.rpm)
	sha1sums+=('9bb5489b6be1713f82b2b0505b35be3447c0c570')
elif [ "$CARCH" == i686 ]; then
	source+=(https://dl.google.com/linux/chrome/rpm/stable/i386/google-chrome-${_channel}-${_verbld}.i386.rpm)
	sha1sums+=('133446732c91233cb9e3cdde6c64a5312d65e704')
fi

package() {
	install -d "${pkgdir}/usr/lib/chromium"
	install -m644 opt/google/chrome/libpdf.so "${pkgdir}/usr/lib/chromium"
	install -Dm644 "${srcdir}/license.html" "${pkgdir}/usr/share/licenses/${pkgname}/license.html"
}

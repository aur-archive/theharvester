# Contributor: WorMzy Tykashi <wormzy.tykashi@gmail.com>
# Contributor: fnord0 <fnord0 AT riseup DOT net>

pkgname=theharvester
_pkgname=theHarvester
pkgver=2.2a
pkgrel=1
pkgdesc="Python tool for gathering e-mail accounts and subdomain names from different public sources (search engines, pgp key servers)"
url="https://code.google.com/p/${pkgname}"
arch=('i686' 'x86_64')
license=('GPL2')
depends=('python2')
source=("https://theharvester.googlecode.com/files/${_pkgname}-${pkgver}.tar.gz")
md5sums=('5b1d9f3e71c801dfb109e8c35ec32f27')
sha1sums=('e02661ed6dd8d9d48d476ccee99878e15f67842a')

package() {
    cd "${srcdir}/${_pkgname}-${pkgver}"
    sed -i '1s|python|python2|' ${_pkgname}.py
    install -Dm755 "${srcdir}/${_pkgname}-${pkgver}/${_pkgname}.py" "${pkgdir}/usr/share/${pkgname}/${_pkgname}.py"
    install -m644 myparser.py "${pkgdir}/usr/share/${pkgname}/myparser.py"
    cp -r discovery "${pkgdir}/usr/share/${pkgname}/"
    cp -r lib "${pkgdir}/usr/share/${pkgname}/"
    install -Dm644 README "${pkgdir}/usr/share/${pkgname}/doc/README"

    mkdir -p "${pkgdir}/usr/bin"
    ln -s "/usr/share/${pkgname}/${_pkgname}.py" "${pkgdir}/usr/bin/${pkgname}"
}

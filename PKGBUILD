# Maintainer: Arch Haskell Team <arch-haskell@haskell.org>
_hkgname=Fungi
pkgname=fungi
pkgver=1.0.4
pkgrel=2
pkgdesc="An interpreter for Funge-98 programming languages, including Befunge."
url="http://hackage.haskell.org/package/${_hkgname}"
license=('custom:BSD3')
arch=('i686' 'x86_64')
makedepends=('ghc' 'haskell-listzipper>=1.2' 'haskell-bytestring=0.9.1.7' 'haskell-containers=0.3.0.0' 'haskell-directory=1.0.1.1' 'haskell-filepath=1.1.0.4' 'haskell-haskell98=1.0.1.1' 'haskell-mtl>=1.1' 'haskell-mwc-random>=0.8' 'haskell-old-time=1.0.0.5' 'haskell-process=1.0.1.3' 'haskell-random=1.0.0.2' 'haskell-tuple>=0.2')
depends=('gmp')
options=('strip')
source=(http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz)
build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup configure --prefix=/usr --docdir=/usr/share/doc/${pkgname} -O
    runhaskell Setup build
}
package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
    install -D -m644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
    rm -f ${pkgdir}/usr/share/doc/${pkgname}/LICENSE
}
md5sums=('363585c5aa19800b5f40168d263d418f')

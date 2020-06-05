pkgname=julia-bin
pkgver=1.4.2
pkgrel=1
arch=('x86_64' 'aarch64')
pkgdesc='High-level, high-performance, dynamic programming language - official binaries'
provides=(julia)
conflicts=(julia)
url='https://julialang.org/'
license=('MIT')
options=(!strip)

case "$CARCH" in
  aarch64) _pkgarch="aarch64"
    sha256sums=('f124d1b9fa68c3049d4ffe2349454f8ba1753d17d6578bc6e7cb916aed7cff4a')
    source=("https://julialang-s3.julialang.org/bin/linux/${_pkgarch}/${pkgver:0:3}/julia-${pkgver}-linux-${_pkgarch}.tar.gz")
    ;;
  x86_64) _pkgarch="x64"
    sha256sums=('d77311be23260710e89700d0b1113eecf421d6cf31a9cebad3f6bdd606165c28')
    source=("https://julialang-s3.julialang.org/bin/linux/${_pkgarch}/${pkgver:0:3}/julia-${pkgver}-linux-x86_64.tar.gz")
    ;;
esac


package() {
  mkdir -p ${pkgdir}/usr/share/licenses/julia
  cp -r julia-${pkgver}/{bin,etc,include,lib,share} ${pkgdir}/usr/
  install -Dm644 julia-${pkgver}/LICENSE.md \
      ${pkgdir}/usr/share/licenses/julia/LICENSE.md
}

# vim: ts=2 sw=2 et:


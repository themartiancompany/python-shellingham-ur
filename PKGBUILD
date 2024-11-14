# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>
# Maintainer: Clint Valentine <valentine.clint@gmail.com>

_py="python"
_pyver="$( \
  "${_py}" \
    -V | \
    awk \
      '{print $2}')"
_pymajver="${_pyver%.*}"
_pyminver="${_pymajver#*.}"
_pynextver="${_pymajver%.*}.$(( \
  ${_pyminver} + 1))"
_pkg=shellingham
pkgbase="${_py}-${_pkg}"
pkgname=(
  "${_py}-${_pkg}"
)
pkgver=1.3.0
pkgrel=1
_pkgdesc=(
  "Detect what shell the current"
  "Python executable is running in."
)
pkgdesc="${_pkgdesc[*]}"
arch=(
  'any'
)
_http="https://github.com"
_ns="sarugaku"
url="${_http}/${_ns}/${_pkg}"
license=(
  'ISC'
)
makedepends=(
  "${_py}>=${_pymajver}"
  "${_py}<${_pynextver}"
  "${_py}-setuptools"
)
options=(
  !emptydirs
)
_pypi="https://pypi.io/packages/source"
source=(
  "${pkgname}-${pkgver}.tar.gz::${_pypi}/${_pkg:0:1}/${_pkg}/${_pkg}-${pkgver}.tar.gz")
sha256sums=(
  'a1bc8cbe437e5348c242d4e8145242d364d9493034ed790a82991c0e2d3ad984'
)

package() {
  cd \
    "${srcdir}/${_pkg}-${pkgver}"
  "${_py}" \
    setup.py \
      install \
        --root="${pkgdir}" \
	--optimize=1
}

build(){
  cd \
    "${srcdir}"/"${_pkg}"-"${pkgver}"
  "${_py}" \
    setup.py \
      build
}

# package_python-shellingham() {
#   cd \
#     "${_pkg}-${pkgver}"
#   install \
#     -Dm644 \
#     LICENSE \
#     "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE" \
#   "${_py}" \
#     setup.py \
#       install \
#         --root="${pkgdir}" \
# 	--optimize=1 \
# 	--skip-build
# }

#!/bin/bash

# Created from the original PKGBUILD by Caleb Maclennan <caleb@alerque.com> and Guillaume Horel <guillaume.horel@gmail.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/python-cu2qu/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/python-cu2qu/discussions>

_langname="python"
_relname="cu2qu"

pkgname="${_langname}-${_relname}"
pkgver=1.6.7.post1
pkgrel=2
pkgdesc="Cubic-to-quadratic bezier curve conversion"
arch=(
  "any"
)
url="https://github.com/googlefonts/cu2qu"
license=(
  "Apache"
)
depends=(
  "python"
  "python-defcon"
  "python-fonttools"
  "python-fs"
)
makedepends=(
  "cython"
  "python-setuptools-scm"
)
checkdepends=(
  "python-coverage"
  "python-pytest-runner"
)
_tarname="$_relname-$pkgver"
source=(
  "https://files.pythonhosted.org/packages/source/${_relname::1}/$_relname/$_tarname.zip"
)
sha512sums=(
  "a0dbed28403ae2bbdbf4719d9e34d5861250dc1510129d658b336d773a5153e0955d5f2ff018f5f93d88394658918fad2a58aebb99cef998d4cf9128a300f489"
)

build() {

  cd "$_tarname"

  python setup.py build
}

check() {

  cd "$_tarname"

  python setup.py test
}

package() {

  cd "$_tarname"

  python setup.py install --root="$pkgdir" --optimize=1 --skip-build
}

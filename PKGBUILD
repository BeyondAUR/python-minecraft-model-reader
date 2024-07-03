# Maintainer: Kimiblock Moe
_name="Minecraft-Model-Reader"
pkgname=python-minecraft-model-reader
pkgdesc="Minecraft-Model-Reader for Amulet-Core"
license=(custom)
arch=(any)
pkgver=1.4.2
pkgrel=1
url="https://github.com/gentlegiantJGC/Minecraft-Model-Reader"
makedepends=(python-build python-installer python-wheel)
depends=(python)
source=(
	"${pkgname}-${pkgver}"::"https://github.com/gentlegiantJGC/${_name}/archive/refs/tags/${pkgver}.tar.gz"
)
md5sums=(
	"75c9e8ca8925cc154b5f5d3c22169b67"
)

function prepare() {
	sed -i 's/versioneer-518/versioneer/g' "${srcdir}/Minecraft-Model-Reader-${pkgver}/pyproject.toml"
}

function build() {
	cd "${srcdir}/${_name}-${pkgver}"
	python -m build --wheel --no-isolation
}

function package() {
	cd "${srcdir}/${_name}-${pkgver}"
	python -m installer --destdir="${pkgdir}" dist/*.whl
}


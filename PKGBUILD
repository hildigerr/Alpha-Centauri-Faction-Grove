# Maintainer: Hildigerr Vergaray <Maintainer at YmirSystems dot com>

_pkgname=alpha-centauri
pkgname=alpha-centauri-grove
pkgver=1.0
pkgrel=0
pkgdesc="Data for Sid Meier's Planetary Pack including a custom faction and rebalancing"
arch=('x86_64')
url="https://github.com/hildigerr/Alpha-Centauri-Faction-Grove"
license=('unknown')
depends=()
provides=(alpha-centauri-data)
conflicts=(alpha-centauri-data)
options=(!strip)
source=(
  "https://archive.org/download/loki-linux-game-isos/%5BLinux%5D%20Alpha%20Centauri/Alpha_Centauri.iso"
  "${pkgname}.tar.gz::${url}/archive/refs/tags/v${pkgver}.tar.gz"
)
md5sums=(
  'b5e765028456de46a2343c996c3a0583'
  'fad2c3f66f65a9f76b8c5c8db86b7255'
)
package() {
  cd "${srcdir}"
  find data -type f -exec install -Dm644 "{}" "${pkgdir}/opt/${_pkgname}/{}" \;
  tar -xzvf "data.tar.gz" --mode=0644 --directory="${pkgdir}/opt/${_pkgname}"
  cd Alpha-Centauri-Faction-Grove-$pkgver
  find . -type f -name "*.[pt][cx][xt]" -exec install -Dm644 "{}" "${pkgdir}/opt/${_pkgname}/data/{}" \;
  chown -R root:root "${pkgdir}/opt/${_pkgname}"
}


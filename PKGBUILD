# Contributor: Andre Renaud <{andrepleblanc,renaudtrudel}@gmail.com>
# Contributor: Marius Muja
# Maintainer: Aaron Ali <t0nedef@causal.ca>
pkgname=xbmc-addon-canada-on-demand-git
pkgver=20130313
pkgrel=2
pkgdesc="XBMC video plugin for streaming live and pre-recorded content from Canadian websites"
arch=('any')
url="http://github.com/marius-muja/plugin.video.canada.on.demand"
license=('GPL')
depends=('xbmc')
install=install
makedepends=('git')
provides=(xbmc-addon-canada-on-demand)
conflicts=(xbmc-addon-canada-on-demand)

_gitroot="git://github.com/marius-muja/plugin.video.canada.on.demand.git"
_gitname="plugin.video.canada.on.demand"

build() {
	cd ${srcdir}/
	msg "Connecting to the GIT server...."
	if [[ -d ${srcdir}/${_gitname} ]] ; then
		cd ${_gitname}
		git pull origin
		msg "The local files are updated..."
	else
		git clone ${_gitroot}
	fi
	msg "GIT checkout done. Building."
}

package() {
	mkdir -p ${pkgdir}/usr/share/xbmc/addons/${_gitname}
	for target in `ls ${srcdir}/$_gitname`; do
		cp -r ${srcdir}/${_gitname}/$target ${pkgdir}/usr/share/xbmc/addons/${_gitname}/.
	done
}

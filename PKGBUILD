# Maintainer : Martin Wimpress <code@flexion.org>
# Contributor: Giovanni Ricciardi <kar98k.sniper@gmail.com>
# Contributor: Xpander <xpander0@gmail.com>

pkgname=mate-panel
pkgver=1.6.1
pkgrel=4
pkgdesc="The MATE Panel"
url="http://mate-desktop.org"
arch=('i686' 'x86_64' 'armv6h' 'armv7h')
license=('GPL')
depends=('dbus-glib' 'dconf' 'gtk2' 'libmatewnck' 'libcanberra' 'libice'
         'libmateweather' 'librsvg' 'libsm'
         'libsoup' 'libxau' 'mate-desktop' 'mate-file-manager'
         'mate-menus' 'mate-session-manager' 'mate-window-manager')
makedepends=('gobject-introspection' 'mate-common' 'mate-doc-utils'
             'networkmanager' 'perl-xml-parser')
options=('!emptydirs')
groups=('mate')
source=("http://pub.mate-desktop.org/releases/1.6/${pkgname}-${pkgver}.tar.xz")
sha1sums=('ccd8d01e14d12d09a9c807b98990c02868323c71')
install=${pkgname}.install

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    ./configure \
        --prefix=/usr \
        --libexecdir=/usr/lib/${pkgname} \
        --sysconfdir=/etc \
        --localstatedir=/var \
        --enable-introspection \
        --disable-static \
        --disable-scrollkeeper
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
}

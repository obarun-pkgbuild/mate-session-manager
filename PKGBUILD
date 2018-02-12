# Maintainer: Eric Vidal <eric@obarun.org>
# based on the original https://git.archlinux.org/svntogit/community.git/tree/trunk?h=packages/mate-session-manager
# 						Contributor: Martin Wimpress <code@flexion.org>

pkgname=mate-session-manager
pkgver=1.20.0
pkgrel=2
pkgdesc="The MATE Session Handler"
url="http://mate-desktop.org"
arch=('x86_64')
license=('GPL')
depends=('dbus-glib' 'gtk3' 'libsm' 'mate-desktop')
makedepends=('intltool' 'xtrans' 'python')
optdepends=('gnome-keyring: keyring support'
            'xdg-user-dirs-gtk: manage user directories')
groups=('mate')
conflicts=('mate-session-manager-gtk3')
replaces=('mate-session-manager-gtk3')
source=("http://pub.mate-desktop.org/releases/${pkgver%.*}/${pkgname}-${pkgver}.tar.xz")
sha256sums=('4f5c4068f3e1f4d63bb86340b375c2f73dec8fb54066d7da589f70a89337f96f')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

build() {
    cd ${pkgname}-${pkgver}
    ./configure \
        --prefix=/usr \
        --libexecdir=/usr/lib/${pkgname} \
        --sysconfdir=/etc \
        --localstatedir=/var \
        --enable-upower \
        --without-systemd
    make
}

package() {
    cd ${pkgname}-${pkgver}
    make DESTDIR="${pkgdir}" install
}

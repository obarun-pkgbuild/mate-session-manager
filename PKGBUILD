# Maintainer: Eric Vidal <eric@obarun.org>
# based on the original https://git.archlinux.org/svntogit/community.git/tree/trunk?h=packages/mate-session-manager
# 						Contributor: Martin Wimpress <code@flexion.org>

pkgname=mate-session-manager
pkgver=1.18.2
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
sha256sums=('40f6bfdfc8945732bda183224d6ecf5b84e6b5bf8b5556bdabc96644bf3a3186')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

build() {
    cd ${pkgname}-${pkgver}
    ./configure \
        --prefix=/usr \
        --libexecdir=/usr/lib/${pkgname} \
        --sysconfdir=/etc \
        --localstatedir=/var \
        --disable-upower \
        --without-systemd
    make
}

package() {
    cd ${pkgname}-${pkgver}
    make DESTDIR="${pkgdir}" install
}

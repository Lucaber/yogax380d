# Maintainer: lucaber <luca@berneking.net>

pkgname='yogax380d-git'
_pkgname='yogax380d'
pkgver=r18.37e99a7
pkgrel=1
pkgdesc='A python daemon which automatically enables tablet mode on the Thinkpad X380 Yoga. This means switching off the TouchPad and TrackPoint. The script can also disable the Finger Input if the Pen is in use. It will optionally rotate the screen.'
url="https://github.com/lucaber/yogax380d"
source=('yogax380d::git+https://github.com/lucaber/yogax380d')
license=('GPL3')
arch=('any')
depends=('xorg-xrandr' 'acpid' 'python-dbus' 'iio-sensor-proxy' 'python-docopt' 'xorg-xinput' 'xf86-input-wacom' 'python')
md5sums=('SKIP')
makedepends=('git')

pkgver() {
    cd "$_pkgname"
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
    cd $srcdir/$_pkgname
    # yogax380d binary
    install -Dm755 "yogax380d" "${pkgdir}/usr/local/bin/yogax380d"

}

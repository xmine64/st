# Suckless Terminal
# Maintainer: Mohammad Amin Mollazadeh <the.madamin20@gmail.com>

pkgname=st-mmdmine
pkgver=staging
pkgrel=1
pkgdesc='Suckless Terminal with Patches'
arch=('x86_64')
license=('MIT')
depends=(libxft)
url=https://st.suckless.org
provides=('st')
conflicts=('st')

_makeopts="--directory=$BUILDDIR"

build() {
  make $_makeopts X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  local installopts='--mode 0644 -D --target-directory'
  local shrdir="$pkgdir/usr/share"
  local licdir="$shrdir/licenses/$pkgname"
  local docdir="$shrdir/doc/$pkgname"
  make $_makeopts PREFIX=/usr DESTDIR="$pkgdir" install
  install $installopts "$licdir" "$BUILDDIR/LICENSE"
  install $installopts "$docdir" "$BUILDDIR/README"
  install $installopts "$shrdir/$pkgname" "$BUILDDIR/st.info"
}

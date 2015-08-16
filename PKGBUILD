#Maintainer: Andrzej Giniewicz <gginiu@gmail.com>
#Contributor: TDY <tdy@gmx.com>

pkgname=hgview
pkgver=1.6.2
pkgrel=1
pkgdesc="A fast Mercurial log navigator"
arch=('any')
url="http://www.logilab.org/project/hgview/"
license=('GPL')
depends=('mercurial>=1.1')
optdepends=('python2-pyqt: for Qt interface'
            'python2-qscintilla: for Qt interface'
            'python2-docutils: for Qt interface'
            'python2-urwid: for CLI interface'
            'python2-pyinotify: for CLI interface'
            'python2-pygments: for CLI interface')
makedepends=('python2-pyqt' 'python2-qscintilla' 'python2-docutils'
             'python2-urwid' 'python2-pyinotify' 'python2-pygments'
             'asciidoc' 'xmlto')
source=(http://download.logilab.org/pub/$pkgname/$pkgname-$pkgver.tar.gz)
md5sums=('5df48bc66e15d8a4014874bc8e6d4ed2')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  python2 setup.py build
}

package() {
  cd "$srcdir/$pkgname-$pkgver"

  python2 setup.py install --root="$pkgdir"/ --optimize=1

  # fix man page placement
  install -d "$pkgdir"/usr/share
  mv "$pkgdir"/usr/man "$pkgdir"/usr/share/man
}


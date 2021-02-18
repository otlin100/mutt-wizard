# Maintainer      :  Kr1ss $(echo \<kr1ss+x-yandex+com\>|sed s/\+/./g\;s/\-/@/)
# Upstream author :  Luke Smith <https://git{hub,lab}.com/lukesmithxyz/>


pkgname=mutt-wizard-lin-git
pkgver() {
  cd "$srcdir/${pkgname%-lin-git}"
  printf 'r%s.g%s' "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}
pkgver=r784.g5f5c617
pkgrel=1

pkgdesc='A simple interface to auto-configure neomutt and isync with safe passwords'
arch=('x86_64')
url='https://github.com/otlin100/mutt-wizard'
license=('GPL3')

provides=("${pkgname%-lin-git}")
conflicts=("${pkgname%-lin-git}")

makedepends=('git')
depends=('neomutt' 'abook' 'isync' 'msmtp' 'notmuch-runtime' 'gopass' 'w3m' 'dunst' 'lynx')
optdepends=('imagemagick: view images inside of the neomutt TUI'
            'links: view HTML email inside of the neomutt TUI'
            'elinks: view HTML email inside of the neomutt TUI'
            'urlview: list URLs found in mails to open them in a browser'
            'cronie: auto-sync mails - alt.: fcron'
            'fcron: auto-sync mails - alt.: cronie'
            'libnotify: enable desktop notifications about new mail'
            'pam-gnupg: automatically unlock gpg keys at session login')

options=('zipman')

source=("git+$url")
sha256sums=('SKIP')

package() {
  cd "$srcdir/${pkgname%-lin-git}"
  make PREFIX=/usr DESTDIR="$pkgdir" -s install
  install -Dm644 -t "$pkgdir/usr/share/doc/${pkgname%-lin-git}/" README.md
}


# vim: ts=2 sw=2 et ft=PKGBUILD:

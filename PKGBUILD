# Generated by gem2arch (https://github.com/anatol/gem2arch)
# Maintainer: Anatol Pomozov <anatol.pomozov@gmail.com>

_gemname=chef-zero
pkgname=ruby-$_gemname-2
pkgver=2.2.1
pkgrel=1
pkgdesc='Self-contained, easy-setup, fast-start in-memory Chef server for testing and solo setup purposes'
arch=(any)
url='http://www.opscode.com'
license=('Apache 2.0')
depends=(ruby ruby-mixlib-log ruby-hashie-2 ruby-ffi-yajl ruby-rack)
options=(!emptydirs)
source=(https://rubygems.org/downloads/$_gemname-$pkgver.gem)
noextract=($_gemname-$pkgver.gem)
sha1sums=('d4d0d7969ad38abf6865d62260f93c07a0d128c1')

package() {
  local _gemdir="$(ruby -e'puts Gem.default_dir')"
  gem install --ignore-dependencies --no-user-install -i "$pkgdir/$_gemdir" -n "$pkgdir/usr/bin" $_gemname-$pkgver.gem
  rm "$pkgdir/$_gemdir/cache/$_gemname-$pkgver.gem"
  install -D -m644 "$pkgdir/$_gemdir/gems/$_gemname-$pkgver/LICENSE" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  # non-HEAD version should not install any files in /usr/bin
  rm -r "$pkgdir/usr/bin/"
}

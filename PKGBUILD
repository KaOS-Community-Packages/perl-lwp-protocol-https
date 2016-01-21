pkgname=perl-lwp-protocol-https
pkgver=6.06
pkgrel=1
pkgdesc="Provide https support for LWP::UserAgent"
arch=('x86_64')
url="https://metacpan.org/release/LWP-Protocol-https"
license=('PerlArtistic' 'GPL')
depends=('ca-certificates' 'perl-io-socket-ssl' 'perl-net-http' 'perl-libwww')
options=('!emptydirs')
source=("http://search.cpan.org/CPAN/authors/id/M/MS/MSCHILLI/LWP-Protocol-https-$pkgver.tar.gz"
        certs.patch)
md5sums=('06f5dfd33b07f6594a429dbbd5e6a2d1'
         'eeee7bb02869fdf17beeceaa8b36c855')

prepare() {
  cd LWP-Protocol-https-${pkgver}
  patch -p0 -i ../certs.patch
}

build() {
  cd LWP-Protocol-https-${pkgver}
  perl Makefile.PL INSTALLDIRS=vendor
  make
}

check() {
  cd LWP-Protocol-https-${pkgver}
  make test
}

package() {
  cd LWP-Protocol-https-${pkgver}
  make DESTDIR="$pkgdir" install
}

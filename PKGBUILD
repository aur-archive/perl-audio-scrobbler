# Maintainer: Jakob Nixdorf <flocke [swirly thing] shadowice [dot] org>

pkgname=perl-audio-scrobbler
pkgver=0.01
pkgrel=1
pkgdesc="Perl interface to audioscrobbler.com/last.fm"
depends=('perl>=5.10.0' 'glibc' 'perl-config-inifiles' 'perl-libwww')
license=('GPL' 'PerlArtistic')
url="http://search.cpan.org/dist/Audio-Scrobbler"
source=(http://search.cpan.org/CPAN/authors/id/R/RO/ROAM/Audio-Scrobbler-$pkgver.tar.gz)
md5sums=('514202239941199ba959e1d68167db6c')
options=('!emptydirs')
arch=(any)

build()
{
  cd ${srcdir}/Audio-Scrobbler-$pkgver

  perl Makefile.PL INSTALLDIRS=vendor || return 1
  make || return 1
  make DESTDIR=${pkgdir} install || return 1
  
  # Remove .packlist and perllocal.pod files.
  find ${pkgdir} -name '.packlist' -delete
  find ${pkgdir} -name 'perllocal.pod' -delete

}


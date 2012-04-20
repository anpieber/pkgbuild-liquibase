# $Id$
# Maintainer: Andreas Pieber <anpieber@gmail.com>

pkgname=liquibase
pkgver=2.0.4
pkgrel=1
pkgdesc="A database management tool"
arch=('any')
url="http://www.liquibase.org/"
license=('APACHE')
depends=('java-environment')
source=(https://github.com/downloads/liquibase/liquibase/liquibase-$pkgver-bin.tar.gz
	liquibase.sh)
md5sums=('1e0586333edae8b45d78b274e1a5d5dc'
         'c484d4bb165302b261c96dcd2acc6da9')

build() {
  # create folders
  mkdir -p $pkgdir/opt/liquibase

  # install profile file
  install -D -m 755 $srcdir/liquibase.sh $pkgdir/etc/profile.d/liquibase.sh

  # move liquibase tar content to /opt/liquibase
  cp -r $srcdir/* $pkgdir/opt/liquibase

  # make liquibase executable
  chmod +x $pkgdir/opt/liquibase/liquibase

  # remove created, but not required data
  rm liquibase-$pkgver-bin.tar.gz
  rm liquibase.sh
}


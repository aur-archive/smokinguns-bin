# Maintainer: Jason Peters <dusk22@gmail.com>

pkgname=smokinguns-bin
pkgver=1.1
pkgrel=5
pkgdesc='A semi-realistic simulation of the "old west" great atmosphere built on id Tech 3.'
arch=('i686' 'x86_64')
url='http://www.smokin-guns.org'
license=('GPL2' 'custom')
depends=('openal')
if [ "$CARCH" == "x86_64" ]; then
  depends+=('lib32-sdl')
fi
replaces=('westernquake3')
options=('!strip')
source=("http://www.smokin-guns.org/downloads/Smokin_Guns_1.1.zip"
	"SmokinGuns.desktop"
	"smokinguns.sh"
	"smokinguns_server.sh")
md5sums=('f6eac64fa534fa9ff121dda5fd2dba44'
	 '4707f551e157914a7e34683a8a1abe15'
	 '04c3627eb9f81e7849f2bdcd9ac69060'
	 'af22a88cfcc623ec15331ddbb133c777')
package() {
  cd "$srcdir/Smokin' Guns $pkgver"
  install -d "$pkgdir/opt/SmokinGuns/baseq3"
  install -m 644 baseq3/* "$pkgdir/opt/SmokinGuns/baseq3"
  install -d "$pkgdir/opt/SmokinGuns/smokinguns"
  install -m 644 smokinguns/* "$pkgdir/opt/SmokinGuns/smokinguns"  
  install -Dm 755 "$startdir/smokinguns.sh" "$pkgdir/usr/bin/smokinguns"
  install -Dm 755 "$startdir/smokinguns_server.sh" "$pkgdir/usr/bin/smokinguns_server"
  install -Dm 775 "$startdir/SmokinGuns.desktop" "$pkgdir/usr/share/applications/Smokin' Guns.desktop"
  install -Dm 644 "LICENSE.txt" "$pkgdir/usr/share/licenses/smokinguns/LICENSE"
  install -Dm 644 "sg_48.png" "$pkgdir/usr/share/pixmaps/smokinguns.png"
  install -m 775 "smokinguns.i386" "$pkgdir/opt/SmokinGuns/smokinguns.bin"
  install -m 775 "smokinguns_dedicated.i386" "$pkgdir/opt/SmokinGuns/smokinguns_dedicated.bin"
}

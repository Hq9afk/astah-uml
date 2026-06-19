# Maintainer: hq9afk <hieubuiduc1@gmail.com>
pkgname=astah-uml
pkgver=11.0.0
pkgrel=1
pkgdesc="UML diagramming tool by Change Vision"
arch=('any')
url="https://astah.net/"
license=('custom')
depends=('java-runtime')
source=("${pkgname}-${pkgver}.zip::https://members.change-vision.com/old/files/_tDNnBRcGKJLvUYn0XavcPEj5LfwPeFpS/astah_UML/11_0_0/astah-uml-11_0_0-ba221e.zip")
# Official MD5 (from https://members.change-vision.com/old/files/astah_UML/11_0_0):
#   974d8a7ce91d0405e1068fd7cea3bd83
sha256sums=('9bd1093e27826df8e1ef8906d0b7127fa6d91c0833ec397d4613b79bc46c701a')

package() {
  install -dm755 "$pkgdir/opt/$pkgname"
  cp -r "$srcdir/astah_uml/." "$pkgdir/opt/$pkgname/"

  install -dm755 "$pkgdir/usr/bin"
  cat > "$pkgdir/usr/bin/$pkgname" <<EOF
#!/bin/sh
exec java -jar /opt/$pkgname/astah-uml.jar -nojvchk "\$@"
EOF
  chmod 755 "$pkgdir/usr/bin/$pkgname"

  install -Dm644 "$srcdir/astah_uml/astah.ico" "$pkgdir/usr/share/pixmaps/$pkgname.ico"

  install -dm755 "$pkgdir/usr/share/applications"
  cat > "$pkgdir/usr/share/applications/$pkgname.desktop" <<EOF
[Desktop Entry]
Name=Astah UML
Exec=$pkgname %f
Icon=$pkgname
Type=Application
Categories=Development;
Terminal=false
MimeType=application/x-asta;
EOF

  install -Dm644 /dev/stdin "$pkgdir/usr/share/mime/packages/$pkgname.xml" <<EOF
<?xml version="1.0"?>
<mime-info xmlns="http://www.freedesktop.org/standards/shared-mime-info">
  <mime-type type="application/x-asta">
    <comment>Astah UML file</comment>
    <glob pattern="*.asta"/>
  </mime-type>
</mime-info>
EOF
}

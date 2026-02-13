pkgname=codium
pkgver=1.109.31074
pkgrel=1
pkgdesc="Binary releases of VSCodium"
arch=('x86_64')
url="https://vscodium.com"
license=('MIT')

depends=(
  'gtk3'
  'libxss'
  'nss'
  'alsa-lib'
  'libnotify'
  'libsecret'
)
optdepends=('gnome-keyring: keyring support')

conflicts=('visual-studio-code-bin')
provides=('vscode')

source=(
  "codium-${pkgver}.tar.gz::https://github.com/VSCodium/vscodium/releases/download/${pkgver}/VSCodium-linux-x64-${pkgver}.tar.gz"
  "codium.desktop"
)

sha256sums=('SKIP' 'SKIP')

package() {
  cd "$srcdir"

  # Install application files (flat tarball layout)
  install -d "${pkgdir}/opt/codium"
  cp -r ./* "${pkgdir}/opt/codium"

  # Remove build artifacts accidentally copied
  rm -f "${pkgdir}/opt/codium/PKGBUILD"
  rm -f "${pkgdir}/opt/codium/codium.desktop"

  # Binary symlink
  install -d "${pkgdir}/usr/bin"
  ln -s /opt/codium/bin/codium "${pkgdir}/usr/bin/codium"

  # Desktop entry
  install -Dm644 codium.desktop \
    "${pkgdir}/usr/share/applications/codium.desktop"

  # Icon
  install -Dm644 \
    "${pkgdir}/opt/codium/resources/app/resources/linux/code.png" \
    "${pkgdir}/usr/share/icons/hicolor/512x512/apps/vscodium.png"

  # License
  install -Dm644 \
    "${pkgdir}/opt/codium/resources/app/LICENSE.txt" \
    "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
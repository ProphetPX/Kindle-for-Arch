# Maintainer: ProphetPX <prophetpx@gmail.com>
pkgname=kindle-for-arch
pkgver=1.0.0
pkgrel=2
pkgdesc="A simple Kindle desktop app for Arch Linux based on Electron"
arch=('any')
url="https://github.com/ProphetPX/Kindle-for-Arch"
license=('MIT')
depends=('electron' 'nodejs' 'npm')
source=('kindle.desktop' 'Kindle.png' 'main.js' 'package.json' 'package-lock.json')
sha256sums=('SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP')

package() {
    # 1. Create the system directory for the app
    install -d "${pkgdir}/usr/lib/${pkgname}"

    # 2. Copy your local files directly into that directory
    cp "${srcdir}/main.js" "${pkgdir}/usr/lib/${pkgname}/"
    cp "${srcdir}/package.json" "${pkgdir}/usr/lib/${pkgname}/"
    cp "${srcdir}/package-lock.json" "${pkgdir}/usr/lib/${pkgname}/"

    # Copy the local assets folder directly from your build directory
    cp -r "${startdir}/assets" "${pkgdir}/usr/lib/${pkgname}/"

    # 3. Install the desktop application launcher shortcut
    install -Dm644 "${srcdir}/kindle.desktop" "${pkgdir}/usr/share/applications/kindle.desktop"

    # 4. Install the application icon
    install -Dm644 "${srcdir}/Kindle.png" "${pkgdir}/usr/share/pixmaps/Kindle.png"

    # 5. Create a system shortcut that bypasses kindle.sh and runs Electron directly
    install -d "${pkgdir}/usr/bin"
    echo -e "#!/bin/sh\nelectron /usr/lib/${pkgname}/main.js \"\$@\"" > "${pkgdir}/usr/bin/kindle"
    chmod +x "${pkgdir}/usr/bin/kindle"
}

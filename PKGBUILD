# Maintainer: Your Name <your.email@example.com>
pkgname=wsl-vpnkit
pkgver=0.4.1
pkgrel=1
pkgdesc="Provides network connectivity to WSL 2 when blocked by VPN"
arch=('x86_64')
url="https://github.com/sakai135/wsl-vpnkit"
license=('MIT')
depends=('iproute2' 'iptables' 'iputils' 'bind' 'wget')
source=("$pkgname-$pkgver.tar.gz::https://github.com/sakai135/wsl-vpnkit/releases/download/v$pkgver/wsl-vpnkit.tar.gz")
sha256sums=('509ef76e6fc0d4d945247b08f323de5b34c6c7ce0b57376680eb8ad7e3a74ed5')

package() {
  cd "$srcdir"
  
  # Install binaries
  install -Dm755 app/wsl-vpnkit "$pkgdir/usr/bin/wsl-vpnkit"
  install -Dm755 app/wsl-gvproxy.exe "$pkgdir/usr/bin/wsl-gvproxy.exe"
  install -Dm755 app/wsl-vm "$pkgdir/usr/bin/wsl-vm"
  
  # Install systemd service
  install -Dm644 app/wsl-vpnkit.service "$pkgdir/usr/lib/systemd/system/wsl-vpnkit.service"
}


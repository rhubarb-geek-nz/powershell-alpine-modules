# Contributor: rhubarb-geek-nz <rhubarb-geek-nz@users.sourceforge.net>
# Maintainer: rhubarb-geek-nz <rhubarb-geek-nz@users.sourceforge.net>
pkgname=powershell-modules
pkgver=7.4.2
pkgrel=0
pkgdesc="PowerShell Modules"
url="https://github.com/rhubarb-geek-nz/powershell-alpine-modules"
arch="noarch"
license="MIT"
depends="powershell=7.4.2-r0"
makedepends=""
checkdepends=""
install=""
subpackages=""
source="https://github.com/PowerShell/PowerShell/releases/download/v7.4.2/powershell-7.4.2-linux-musl-x64.tar.gz"
builddir="$srcdir/"
subpackages="$pkgname-archive:packagearchive $pkgname-packagemanagement:packagepackagemanagement $pkgname-threadjob:packagethreadjob $pkgname-psreadline:packagepsreadline $pkgname-powershellget:packagepowershellget $pkgname-psresourceget:packagepsresourceget"

build() {
	:
}

check() {
	:
}

package() {
	install -d "$pkgdir/usr/lib/powershell/Modules"
}

packagearchive() {
	echo SRCDIR=$srcdir PKGSUBDIR=$subpkgdir 

	install -d "$subpkgdir/usr/lib/powershell/Modules/Microsoft.PowerShell.Archive"
	tar -cf - -C "$srcdir" "Modules/Microsoft.PowerShell.Archive" | tar xf - -C "$subpkgdir/usr/lib/powershell"
}

packagepackagemanagement() {
	install -d "$subpkgdir/usr/lib/powershell/Modules/PackageManagement"
	tar -cf - -C "$srcdir" "Modules/PackageManagement" | tar xf - -C "$subpkgdir/usr/lib/powershell"
}

packagethreadjob() {
	install -d "$subpkgdir/usr/lib/powershell/Modules/ThreadJob"
	tar -cf - -C "$srcdir" "Modules/ThreadJob" | tar xf - -C "$subpkgdir/usr/lib/powershell"
}

packagepsreadline() {
	install -d "$subpkgdir/usr/lib/powershell/Modules/PSReadLine"
	tar -cf - -C "$srcdir" "Modules/PSReadLine" | tar xf - -C "$subpkgdir/usr/lib/powershell"
}

packagepowershellget() {
	install -d "$subpkgdir/usr/lib/powershell/Modules/PowerShellGet"
	tar -cf - -C "$srcdir" "Modules/PowerShellGet" | tar xf - -C "$subpkgdir/usr/lib/powershell"
}

packagepsresourceget() {
	install -d "$subpkgdir/usr/lib/powershell/Modules/Microsoft.PowerShell.PSResourceGet"
	tar -cf - -C "$srcdir" "Modules/Microsoft.PowerShell.PSResourceGet" | tar xf - -C "$subpkgdir/usr/lib/powershell"
}

sha512sums="
9ac7d11d4318bff9348a22573cf6e1dfce8b7dc8f8414e4bbeff6e15cd27d5d5765825cc597cbd95d2eea713e0045f971cc4acde6e85a3d3dd4515090f5353b5  powershell-7.4.2-linux-musl-x64.tar.gz
"

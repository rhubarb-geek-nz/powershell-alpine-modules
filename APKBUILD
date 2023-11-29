# Contributor: rhubarb-geek-nz <rhubarb-geek-nz@users.sourceforge.net>
# Maintainer: rhubarb-geek-nz <rhubarb-geek-nz@users.sourceforge.net>
pkgname=powershell-modules
pkgver=7.4.0
pkgrel=0
pkgdesc="PowerShell Modules"
url="https://github.com/rhubarb-geek-nz/powershell-alpine-modules"
arch="noarch"
license="MIT"
depends="powershell=7.4.0-r0"
makedepends=""
checkdepends=""
install=""
subpackages=""
source="https://github.com/PowerShell/PowerShell/releases/download/v7.4.0/powershell-7.4.0-linux-musl-x64.tar.gz"
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
9397a2eeb691bedb93b201bcdbeb8a62746c055366679c66ef507ce0cf615d902343b1ffba333effe3c045b74ffd8231186227db088d4a4eff4eb34b123a048b  powershell-7.4.0-linux-musl-x64.tar.gz
"

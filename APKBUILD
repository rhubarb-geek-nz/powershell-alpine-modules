# Contributor: rhubarb-geek-nz <rhubarb-geek-nz@users.sourceforge.net>
# Maintainer: rhubarb-geek-nz <rhubarb-geek-nz@users.sourceforge.net>
pkgname=powershell-modules
pkgver=7.3.4
pkgrel=1
pkgdesc="PowerShell Modules"
url="https://github.com/rhubarb-geek-nz/powershell-alpine-modules"
arch="noarch"
license="MIT"
depends="powershell=7.3.4-r1"
makedepends=""
checkdepends=""
install=""
subpackages=""
source="https://github.com/PowerShell/PowerShell/releases/download/v7.3.4/powershell-7.3.4-linux-alpine-x64.tar.gz"
builddir="$srcdir/"
subpackages="$pkgname-archive:packagearchive $pkgname-packagemanagement:packagepackagemanagement $pkgname-threadjob:packagethreadjob $pkgname-psreadline:packagepsreadline $pkgname-powershellget:packagepowershellget"

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

sha512sums="
a997482c5c1499b8f94dece71893de49e3e0af5f8f0fd1dabef3ec788c31ca09607cf5a607420fa244f9dff78877819acfbb25e90d8b831690aa62cb80a4462f  powershell-7.3.4-linux-alpine-x64.tar.gz
"

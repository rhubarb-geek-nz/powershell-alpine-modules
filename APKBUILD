# Contributor: rhubarb-geek-nz <rhubarb-geek-nz@users.sourceforge.net>
# Maintainer: rhubarb-geek-nz <rhubarb-geek-nz@users.sourceforge.net>
pkgname=powershell-modules
pkgver=7.2.7
pkgrel=0
pkgdesc="PowerShell Modules"
url="https://github.com/rhubarb-geek-nz/powershell-alpine-modules"
arch="noarch"
license="MIT"
depends="powershell=7.2.7-r0"
makedepends=""
checkdepends=""
install=""
subpackages=""
source="https://github.com/PowerShell/PowerShell/releases/download/v7.2.7/powershell-7.2.7-linux-alpine-x64.tar.gz"
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
dd53419166ca61051432bacfe782765cac7387fe1bccd8bdc6ab30a86860c0a2bf13e170a08d7e467feec11047df19edf0098d42b3ff30f050aceec969d167f6  powershell-7.2.7-linux-alpine-x64.tar.gz
"

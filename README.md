# PowerShell Modules for Alpine

The purpose of this project is to install the missing modules by building the `apk` directly from PowerShell downloads.

The [APKBUILD](APKBUILD) file describes the packages to build.

The version of the `powershell` package on Alpine is matched with that from the downloads.

Build the project.

```
$ abuild
>>> powershell-modules: Building alpine/powershell-modules 7.4.2-r0 (using abuild 3.12.0-r0) started Tue, 28 Nov 2023 00:36:09 +0000
>>> powershell-modules-archive*: Create powershell-modules-archive-7.4.2-r0.apk
>>> powershell-modules-packagemanagement*: Create powershell-modules-packagemanagement-7.4.2-r0.apk
>>> powershell-modules-powershellget*: Create powershell-modules-powershellget-7.4.2-r0.apk
>>> powershell-modules-psreadline*: Create powershell-modules-psreadline-7.4.2-r0.apk
>>> powershell-modules-threadjob*: Create powershell-modules-threadjob-7.4.2-r0.apk
>>> powershell-modules*: Create powershell-modules-7.4.2-r0.apk
```

Should build the `apk` files.

```
$ ls $HOME/packages/alpine/$(arch) | grep powershell-module
powershell-modules-7.4.2-r0.apk
powershell-modules-archive-7.4.2-r0.apk
powershell-modules-packagemanagement-7.4.2-r0.apk
powershell-modules-powershellget-7.4.2-r0.apk
powershell-modules-psreadline-7.4.2-r0.apk
powershell-modules-threadjob-7.4.2-r0.apk
```

Install with

```
$ sudo apk add $(find $HOME/packages/alpine/$(arch) -name "powershell-modules-*7.4.2-r0.apk")
(1/8) Installing powershell (7.4.2-r0)
(2/8) Installing powershell-modules (7.4.2-r0)
(3/8) Installing powershell-modules-archive (7.4.2-r0)
(4/8) Installing powershell-modules-packagemanagement (7.4.2-r0)
(5/8) Installing powershell-modules-powershellget (7.4.2-r0)
(6/8) Installing powershell-modules-psreadline (7.4.2-r0)
(7/8) Installing powershell-modules-psresourceget (7.4.2-r0)
(8/8) Installing powershell-modules-threadjob (7.4.2-r0)
Executing busybox-1.34.1-r7.trigger
OK: 438 MiB in 96 packages
```

The missing modules should now be present.

```
$ ls /usr/lib/powershell/Modules | sort
Microsoft.PowerShell.Archive
Microsoft.PowerShell.Host
Microsoft.PowerShell.Management
Microsoft.PowerShell.Security
Microsoft.PowerShell.Utility
PSReadLine
PackageManagement
PowerShellGet
ThreadJob
```

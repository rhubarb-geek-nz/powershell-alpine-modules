# PowerShell Modules for Alpine

The purpose of this project is to install the missing modules by building the `apk` directly from PowerShell downloads.

The [APKBUILD](APKBUILD) file describes the packages to build.

The version of the `powershell` package on Alpine is matched with that from the downloads.

Build the project.

```
$ abuild
>>> powershell-modules: Building alpine/powershell-modules 7.4.0-r0 (using abuild 3.12.0-r0) started Tue, 28 Nov 2023 00:36:09 +0000
>>> powershell-modules-archive*: Create powershell-modules-archive-7.4.0-r0.apk
>>> powershell-modules-packagemanagement*: Create powershell-modules-packagemanagement-7.4.0-r0.apk
>>> powershell-modules-powershellget*: Create powershell-modules-powershellget-7.4.0-r0.apk
>>> powershell-modules-psreadline*: Create powershell-modules-psreadline-7.4.0-r0.apk
>>> powershell-modules-threadjob*: Create powershell-modules-threadjob-7.4.0-r0.apk
>>> powershell-modules*: Create powershell-modules-7.4.0-r0.apk
```

Should build the `apk` files.

```
$ ls $HOME/packages/alpine/$(arch) | grep powershell-module
powershell-modules-7.4.0-r0.apk
powershell-modules-archive-7.4.0-r0.apk
powershell-modules-packagemanagement-7.4.0-r0.apk
powershell-modules-powershellget-7.4.0-r0.apk
powershell-modules-psreadline-7.4.0-r0.apk
powershell-modules-threadjob-7.4.0-r0.apk
```

Install with

```
$ sudo apk add $(find $HOME/packages/alpine/$(arch) -name "powershell-modules-*7.4.0-r0.apk")
(1/14) Installing dotnet-host (7.0.14-r0)
(2/14) Installing dotnet7-hostfxr (7.0.14-r0)
(3/14) Installing lttng-ust (2.13.6-r0)
(4/14) Installing xz-libs (5.4.5-r0)
(5/14) Installing libunwind (1.7.2-r1)
(6/14) Installing dotnet7-runtime (7.0.14-r0)
(7/14) Installing libpsl-native (7.3.1-r0)
(8/14) Installing powershell (7.4.0-r0)
(9/14) Installing powershell-modules (7.4.0-r0)
(10/14) Installing powershell-modules-archive (7.4.0-r0)
(11/14) Installing powershell-modules-packagemanagement (7.4.0-r0)
(12/14) Installing powershell-modules-powershellget (7.4.0-r0)
(13/14) Installing powershell-modules-psreadline (7.4.0-r0)
(14/14) Installing powershell-modules-threadjob (7.4.0-r0)
Executing busybox-1.36.1-r15.trigger
OK: 412 MiB in 106 packages
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

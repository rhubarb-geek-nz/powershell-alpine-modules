# PowerShell Modules for Alpine

The purpose of this project is to install the missing modules by building the `apk` directly from PowerShell downloads.

The [APKBUILD](APKBUILD) file describes the packages to build.

The version of the `powershell` package on Alpine is matched with that from the downloads.

Build the project.

```
$ abuild
>>> powershell-modules-archive*: Create powershell-modules-archive-7.2.7-r0.apk
>>> powershell-modules-packagemanagement*: Create powershell-modules-packagemanagement-7.2.7-r0.apk
>>> powershell-modules-powershellget*: Create powershell-modules-powershellget-7.2.7-r0.apk
>>> powershell-modules-psreadline*: Create powershell-modules-psreadline-7.2.7-r0.apk
>>> powershell-modules-threadjob*: Create powershell-modules-threadjob-7.2.7-r0.apk
>>> powershell-modules*: Create powershell-modules-7.2.7-r0.apk
```

Should build the `apk` files.

```
$ ls $HOME/packages/alpine/$(arch) | grep powershell-module
powershell-modules-7.2.7-r0.apk
powershell-modules-archive-7.2.7-r0.apk
powershell-modules-packagemanagement-7.2.7-r0.apk
powershell-modules-powershellget-7.2.7-r0.apk
powershell-modules-psreadline-7.2.7-r0.apk
powershell-modules-threadjob-7.2.7-r0.apk
```

Install with

```
$ sudo apk add $(find $HOME/packages/alpine/$(arch) -name "powershell-modules-*7.2.7-r0.apk")
(1/14) Installing dotnet-host (7.0.4-r0)
(2/14) Installing dotnet6-hostfxr (6.0.15-r0)
(3/14) Installing lttng-ust (2.13.3-r0)
(4/14) Installing xz-libs (5.2.9-r0)
(5/14) Installing libunwind (1.6.2-r0)
(6/14) Installing dotnet6-runtime (6.0.15-r0)
(7/14) Installing libpsl-native (7.2.0-r0)
(8/14) Installing powershell (7.2.7-r0)
(9/14) Installing powershell-modules (7.2.7-r0)
(10/14) Installing powershell-modules-archive (7.2.7-r0)
(11/14) Installing powershell-modules-packagemanagement (7.2.7-r0)
(12/14) Installing powershell-modules-powershellget (7.2.7-r0)
(13/14) Installing powershell-modules-psreadline (7.2.7-r0)
(14/14) Installing powershell-modules-threadjob (7.2.7-r0)
Executing busybox-1.35.0-r29.trigger
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

# PowerShell Modules for Alpine

The purpose of this project is to install the missing modules by building the `apk` directly from PowerShell downloads.

The [APKBUILD](APKBUILD) file describes the packages to build.

The version of the `powershell` package on Alpine is matched with that from the downloads.

Build the project.

```
$ abuild
>>> powershell-modules: Building alpine/powershell-modules 7.3.4-r1 (using abuild 3.11.1-r0) started Tue, 28 Nov 2023 00:36:09 +0000
>>> powershell-modules-archive*: Create powershell-modules-archive-7.3.4-r1.apk
>>> powershell-modules-packagemanagement*: Create powershell-modules-packagemanagement-7.3.4-r1.apk
>>> powershell-modules-powershellget*: Create powershell-modules-powershellget-7.3.4-r1.apk
>>> powershell-modules-psreadline*: Create powershell-modules-psreadline-7.3.4-r1.apk
>>> powershell-modules-threadjob*: Create powershell-modules-threadjob-7.3.4-r1.apk
>>> powershell-modules*: Create powershell-modules-7.3.4-r1.apk
```

Should build the `apk` files.

```
$ ls $HOME/packages/alpine/$(arch) | grep powershell-module
powershell-modules-7.3.4-r1.apk
powershell-modules-archive-7.3.4-r1.apk
powershell-modules-packagemanagement-7.3.4-r1.apk
powershell-modules-powershellget-7.3.4-r1.apk
powershell-modules-psreadline-7.3.4-r1.apk
powershell-modules-threadjob-7.3.4-r1.apk
```

Install with

```
$ sudo apk add $(find $HOME/packages/alpine/$(arch) -name "powershell-modules-*7.3.4-r1.apk")
(1/12) Installing dotnet-host (7.0.14-r0)
(2/12) Installing dotnet7-hostfxr (7.0.14-r0)
(3/12) Installing lttng-ust (2.13.5-r2)
(4/12) Installing dotnet7-runtime (7.0.14-r0)
(5/12) Installing libpsl-native (7.3.1-r0)
(6/12) Installing powershell (7.3.4-r1)
(7/12) Installing powershell-modules (7.3.4-r1)
(8/12) Installing powershell-modules-archive (7.3.4-r1)
(9/12) Installing powershell-modules-packagemanagement (7.3.4-r1)
(10/12) Installing powershell-modules-powershellget (7.3.4-r1)
(11/12) Installing powershell-modules-psreadline (7.3.4-r1)
(12/12) Installing powershell-modules-threadjob (7.3.4-r1)
Executing busybox-1.36.1-r2.trigger
OK: 444 MiB in 101 packages
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

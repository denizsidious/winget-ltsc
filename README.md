# Winget LTSC
A up to date Winget installation guide for Windows 10 (IoT) Enterprise LTSC. 

# Download the essential msixbundle and the License1.xml files: 

https://github.com/microsoft/winget-cli/releases/latest

# Download the VCLibs Desktop framework package associated with your processor architecture.

For x64 architecture: https://aka.ms/Microsoft.VCLibs.x64.14.00.Desktop.appx

For x86 architecture: https://aka.ms/Microsoft.VCLibs.x86.14.00.Desktop.appx

# Download the NuGet dependecy:

https://www.nuget.org/packages/Microsoft.UI.Xaml/

Change the file extension from .nupkg to .zip by renaming it.

Open the .zip folder renamed in the previous step using File Explorer and copy the file tools\AppX\<your architecture>\release\Microsoft.UI.XAML.2.x.appx to your downloads folder. 

# Installing winget-cli

Launch PowerShell as administrator.

```
Add-AppxPackage -Path <path to VCLibs .appx file that you downloaded in second step>
```
```
Add-AppxPackage -Path <path to UI xaml.appx file that you downloaded in third step>
```
```
Add-AppxPackage -Path <path to .msixbundle file that you downloaded in first step>
```
```
Add-AppxProvisionedPackage -Online -PackagePath <path to .msixbundle file> -LicensePath <path to xml file>
```

# Warning

There are a lot of wrong guides about winget installation. This guide will be pretty much enough for you, if you face any issues just let me know.

This guide is updated version of [this](https://learn.microsoft.com/en-us/troubleshoot/developer/visualstudio/cpp/libraries/c-runtime-packages-desktop-bridge) Microsoft article. I just chanded few things in my guide.

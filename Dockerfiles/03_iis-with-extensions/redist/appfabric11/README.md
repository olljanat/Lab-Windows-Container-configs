== Creating AppFabric package for Windows Containers ===
**NOTE!** Installating AppFabric to Windows Server 2016 is not supported by Microsoft but you can do it based on this guide.

* Download "WindowsServerAppFabricSetup_x64.exe" from https://www.microsoft.com/en-us/download/details.aspx?id=27115
* Extract package using command
```
.\WindowsServerAppFabricSetup_x64.exe /x
```
* Copy content of "packages" -folder to this folder (and remove temp files).
* Do following modifications to "appfabric-1.1-for-windows-server-64.msi" -using ORCA:
  * Remove ```Installed OR ((UILevel="2") AND (NOT INSTALLDIR=""))``` from LaunchCondition.
  * Remove following Actions from "InstallExecuteSequence":
    * All "Usergroup_AS..." (needed because net localgroup command does not work inside of containers).
  * Remove following from CustomAction
    * RegisterPerfmonManifest
    * RollbackRegisterPerfmonManifest
    * ConfigurePerfmonManifestRegister
    * UnregisterPerfmonManifest    
    


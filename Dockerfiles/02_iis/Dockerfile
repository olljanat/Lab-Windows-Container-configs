FROM			dotnet35:latest
MAINTAINER		Olli Janatuinen

# Install IIS
RUN				powershell -Command Add-WindowsFeature Web-WebServer,Web-Health,Web-Performance,Web-Security,Web-Asp-Net45,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-AppInit,Web-Scripting-Tools
RUN				powershell -Command Add-WindowsFeature NET-WCF-TCP-Activation45,Web-Custom-Logging,Web-Request-Monitor,Web-Http-Tracing,Web-Basic-Auth,Web-Windows-Auth,Web-Digest-Auth

# Enable event log
RUN				powershell.exe -command Set-ItemProperty HKLM:\SYSTEM\CurrentControlSet\Control\WMI\Autologger\EventLog-Application Start 1


CMD				cmd
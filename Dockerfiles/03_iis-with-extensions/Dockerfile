FROM			    iis:latest
MAINTAINER		    Olli Janatuinen

# Install HTTP and non-HTTP activation to IIS
RUN				    powershell -Command Add-WindowsFeature NET-HTTP-Activation,NET-Non-HTTP-Activ

# Install other IIS extensions
COPY				redist C:/redist/
RUN					msiexec /i "c:\redist\URLrewrite20\rewrite_amd64.msi" /qn
RUN					msiexec /i "c:\redist\appfabric11\appfabric-1.1-for-windows-server-64.msi" /qn

CMD					cmd
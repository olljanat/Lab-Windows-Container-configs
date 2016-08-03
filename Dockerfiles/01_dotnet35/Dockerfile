FROM			    windowsservercore:latest
MAINTAINER		    Olli Janatuinen

# Install .NET 3.5
COPY				sxs C:/sxs/
RUN					dism /online /enable-feature /featurename:NetFX3 /All /Source:C:\sxs\ /LimitAccess

CMD					cmd
QUICK SLPK SERVER
======================

Minimalist web server engine to publish OGC SceneLayerPackage (.slpk) to Indexed 3d Scene Layer (I3S) web service.

Why this projects?  Publishing I3S service to Portal for ArcGIS requires to federated ArcGIS Server ... with this server, you can bypass this step and keep going with your non federated arcgis server.

Why this fork? The original repo no longer works with current versions of ArcGIS JS API. Around 4.14 the library starts to expect some kind of url prefix like `arcgis/rest/services` which is not mentioned in release notes (o.o). Also, the nlsc.slpk test data could not be rendered properly (needs to patch read method to treat `textures/0_0_1.bin` as gzip).

How to use:
- Place .SLPK into a folder (default: "./slpk")  [You can create SLPK with ArcGIS pro and some other softwares]
- Configure the script (quick_slpk_server.py):
	- webserver host
	- webserver port
	- slpk folder
- Launch this script 
- Open browser to "host:port"
- Index page let you access your SLPK as I3S services
-  Also provide an intern viewer for test

- You can use your I3S services on arcgis online, portal for arcgis, arcgis javascript API, ...  simply use ther service url:
	{host}:{port}/{slpk name .slpk}/SceneServer

How to:
- Configure Index page: modify->  views/services_list.tpl
- Configure Viewer page: modify->  views/carte.tpl


Sources:
- python 2.x
- I3S Specifications: https://github.com/Esri/i3s-spec
- BottlePy 0.13+
- Arcgis Javascript API >=4.6

Test data:
- World_earthquakes_2000_2010.slpk (i3s 1.6 points)
- nlsc.slpk (i3s 1.5 integrated-mesh with textures, around Tripoli)


Autor: RIVIERE Romain
Date: 12/02/2018
Licence: GNU GPLv3 

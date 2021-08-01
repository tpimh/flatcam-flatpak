# FlatCAM Flatpak

This is an attempt to package [FlatCAM](http://flatcam.org/) into a [Flatpak](https://flatpak.org/).

I am no expert on building Flatpaks, so the quality is very poor and can be improved a lot. Use it at your own risk, but given the nature of Flatpak the risk should be minimal, and I would be happy if you tried it out 	:)

Parts of this manifest should be moved into separate files, other parts should be rewritten. There is unoptimal compilation there, for example CMake, FreeType (two different versions!) and HarfBuzz are compiled from source, even though they are all a part of the SDK. There must be some unused or missing optional dependencies as well. Any suggestions on how it can be improved are highly appreciated!

The most valuable parts are borrowed from other Flatpaks published in Flathub:

- pyqt5 from [org.qutebrowser.qutebrowser](https://github.com/flathub/org.qutebrowser.qutebrowser/blob/2ba9696140894061f6e46f7fb4a9addd8a9151b7/org.qutebrowser.qutebrowser.yml#L201)
- gdal from [org.qgis.qgis](https://github.com/flathub/org.qgis.qgis/blob/05c19fa122feddb3753daf5dd7d898c7d3fae9e6/org.qgis.qgis.json#L194)

## Building and running

```
flatpak install flathub org.kde.Platform//5.15 org.kde.Sdk//5.15
flatpak-builder --user --install build-dir org.flatcam.FlatCAM.yml
flatpak run org.flatcam.FlatCAM
```

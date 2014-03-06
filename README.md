## FileGDB OGR Plugin

Run the `install` command.

Here's what `install` does:

```sh
#!/bin/sh

cd /Library/Frameworks/GDAL.framework/Versions/Current/PlugIns

echo "Downloading ogr_FileGDB.dylib"
curl -L -# https://github.com/zhm/filegdb-osx/blob/master/lib/ogr_FileGDB.dylib?raw=true > ogr_FileGDB.dylib

echo "Downloading libFileGDBAPI.dylib"
curl -L -# https://github.com/zhm/filegdb-osx/blob/master/lib/libFileGDBAPI.dylib?raw=true > libFileGDBAPI.dylib

echo "Downloading libfgdbunixrtl.dylib"
curl -L -# https://github.com/zhm/filegdb-osx/blob/master/lib/libfgdbunixrtl.dylib?raw=true > libfgdbunixrtl.dylib

echo "FileGDB plugin installed."
```

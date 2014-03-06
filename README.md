## FileGDB OGR Plugin

Run the `install` command.

Here's what `install` does:

```sh
#!/bin/sh

cd /Library/Frameworks/GDAL.framework/Versions/Current/PlugIns

echo "Downloading ogr_FileGDB.dylib"
curl -L -# http://cl.ly/3n013Y2x3W2w/download/ogr_FileGDB.dylib > ogr_FileGDB.dylib

echo "Downloading libFileGDBAPI.dylib"
curl -L -# http://cl.ly/0l1S1w2a2H2L/download/libFileGDBAPI.dylib > libFileGDBAPI.dylib

echo "Downloading libfgdbunixrtl.dylib"
curl -L -# http://cl.ly/0l3R1t1q1f1O/download/libfgdbunixrtl.dylib > libfgdbunixrtl.dylib

echo "FileGDB plugin installed."
```

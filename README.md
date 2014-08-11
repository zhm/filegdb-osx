## FileGDB OGR Plugin

### Simple Installation

```sh
curl -L -# https://raw.githubusercontent.com/zhm/filegdb-osx/master/install | sh
```

### Manual Installation

Run the `install` command.

Here's what `install` does:

```sh
cd /Library/Frameworks/GDAL.framework/Versions/Current/PlugIns

echo "Downloading ogr_FileGDB.dylib"
curl -L -# https://raw.githubusercontent.com/zhm/filegdb-osx/master/lib/ogr_FileGDB.dylib > ogr_FileGDB.dylib

echo "Downloading libFileGDBAPI.dylib"
curl -L -# https://raw.githubusercontent.com/zhm/filegdb-osx/master/lib/libFileGDBAPI.dylib > libFileGDBAPI.dylib

echo "Downloading libfgdbunixrtl.dylib"
curl -L -# https://raw.githubusercontent.com/zhm/filegdb-osx/master/lib/libfgdbunixrtl.dylib > libfgdbunixrtl.dylib

echo "Verifying it works, you should see read/write below."
/Library/Frameworks/GDAL.framework/Versions/Current/Programs/ogr2ogr --formats | grep '"FileGDB" (read/write)'

echo "FileGDB plugin installed."
```

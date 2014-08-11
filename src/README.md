## Building the OGR plugin on Mac

- Download the GDAL source
- You will need GCC 4.9 to build the plugin because the ESRI-distributed dylib plugin was compiled with GCC and it exports C++ symbols
- run `configure` with the `--with-fgdb` switch to setup the global makefile config

```sh
./configure --with-fgdb="$HOME/local/filegdb"
```

- `cd ./ogr/ogrsf_frmts/filegdb`
- Patch the `GNUMakefile` with the contents of `GNUMakefile` in this directory (overwrite file)
- Run the commands in the `build` file in this directory

```sh
make plugin

install_name_tool -change "/usr/local/lib/libgdal.1.dylib" "/Library/Frameworks/GDAL.framework/Versions/Current/GDAL" ogr_FileGDB.dylib
install_name_tool -change "@rpath/libFileGDBAPI.dylib" "/Library/Frameworks/GDAL.framework/Versions/Current/PlugIns/libFileGDBAPI.dylib" ogr_FileGDB.dylib
install_name_tool -change "@rpath/libfgdbunixrtl.dylib" "/Library/Frameworks/GDAL.framework/Versions/Current/PlugIns/libfgdbunixrtl.dylib" ogr_FileGDB.dylib
```

- Test it out

```sh
cp ogr_FileGDB.dylib /Library/Frameworks/GDAL.framework/Versions/Current/PlugIns

/Library/Frameworks/GDAL.framework/Versions/Current/Programs/ogr2ogr --formats | grep FileGDB
```

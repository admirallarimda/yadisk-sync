[![Build Status](https://travis-ci.com/admirallarimda/yadisk-sync.svg?branch=master)](https://travis-ci.com/admirallarimda/yadisk-sync)
# yadisk-sync
Tool for explicit synching files with Yandex.Disk

This tool works via WebDAV protocol, thus you could try it with any other WebDAV-compatible file server.

## How to use
Simply run it like this: _./yadisk-sync --upload --from [from] --to [to] --user admirallarimda_ 

If [from] is a directory, all subsequent directories will be synched as well, preserving directory structure starting from that directory.

File masking is **not yet supported** (i.e. you can't write something like --from *.jpg)

[to] points to the folder where all data should be stored ([to] directory might be missing, the tool will create it automatically)

The tool is capable uploading as well as downloading files from WebDAV server. Just use either _--upload_ or _--download_ flag with correct [from] directory.

Though by default the tool looks at the Yandex.Disk server, you can specify any WebDAV server using _--host_ argument.

## Where to get
All binaries are automatically created for each release. Latest release could be found [here](https://github.com/admirallarimda/yadisk-sync/releases/latest)

## Building
go 1.11 is preferable (due to modules support). Though you should be able to compile with lower versions of go toolset.

Due to [gowebdav memleak](https://github.com/studio-b12/gowebdav/issues/24) not the latest version of the library is used. Once the bug is fixed, I'll update the module.

# Extract game files
## Key
523aad2de7132
## Tested: Five memories; Five promises
## Preparing to test: Summer memories
Using [KaleidoKeyFinderSwitch](https://github.com/Manicsteiner/KaleidoKeyFinderSwitch) to find possible strings in the "main" file.
"main" file can be extracted using Ryujinx.
Example:
```python
main([file])
```
## Methods
Use [Freemote](https://github.com/UlyssesWu/FreeMote) to extract files.
Example:
```powershell
psbdecompile.exe info-psb [psb-m-file] -k [key] -a
```
### Place .bin file and .psb.m file under the same folder.

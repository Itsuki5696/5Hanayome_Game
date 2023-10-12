# Introduction
Games running on Kaleido ADV workshop platform are all encrypted. The key is storaged in the main file, but the position of the key varies between games. According to the author of [KaleidoKeyFinderSwitch](https://github.com/Manicsteiner/KaleidoKeyFinderSwitch), there isn't a perfect method to find the key. However, there are four same properties of keys in every game:

1. The key should be a string contains 13 characters. Games on other platforms may have exceptions.
2. The previous byte of this string is always ```\x00```.
3. The string always contains and only contains numbers and letters, including capital letters.
4. The string is always meaningless and you can not separate any meaningful word from the string.

The author mentioned above tested their code using Anonymous;Code(JP), Gotoubun Five memories and Gotoubun Summer memories. Results seem to be successful, but the code could not find the key when scanning Anonymous;Code(Eng) since the last letter of the string is a character other than letters and numbers.

## Key
```
523aad2de7132
```
## Tested: Five memories; Five promises
## Preparing to test: Summer memories
# Methods
1. Initially extract game files. You can use Ryujinx to extract .nsp or .xci files.

You should get several these kind of files after selecting "RomFS":
```
[name]_info.psb.m
[name]_body.bin
```
Then, find "main" file by selecting "ExeFS".

2. Using [KaleidoKeyFinderSwitch](https://github.com/Manicsteiner/KaleidoKeyFinderSwitch) to find possible strings in the "main" file.

Example:
```python
>>> KeyFinder.py
>>> main([file])
```
The result will like this:
```python
Destination [Number] [KeyValue] (Marked)
```
You can copy those keyvalues with a "marked" sign and try them one by one.

Use [Freemote](https://github.com/UlyssesWu/FreeMote) to extract files.

Example:
```powershell
psbdecompile.exe info-psb [psb-m-file] -k 523aad2de7132 -a
```
### Place .bin file and .psb.m file under the same folder.

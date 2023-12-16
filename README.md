# ResTable Reader/Writer for The Legend of Zelda: Tears of the Kingdom

A  C++ library to read and write RESTBL files.
## Usage
First of all, include the `RESTBL.h` header file. To load a RESTBL file, pass the path to a file or a vector of unsigned bytes to the constructor.
```cpp
#include "RESTBL.h"

int main()
{
    ResTableFile RSTB("ResourceSizeTable.Product.121.rsizetable");
    return 0;
}
```
To get the size of a file, pass the path or the CRC32 hash to the function `GetFileSize`.
```cpp
#include "RESTBL.h"

int main()
{
    ResTableFile RSTB("ResourceSizeTable.Product.121.rsizetable");
    uint32_t Size = RSTB.GetFileSize("Banc/SmallDungeon/Dungeon001_Static.bcett.byml");
    return 0;
}
```
To set the size of a file, call the `SeFileSize` function and pass the path or the CRC32 hash as well as the new size.
```cpp
#include "RESTBL.h"

int main()
{
    ResTableFile RSTB("ResourceSizeTable.Product.121.rsizetable");
    RSTB.SetFileSize("Banc/SmallDungeon/Dungeon001_Static.bcett.byml", 12345);
    return 0;
}
```
To generate a CRC32 hash of a string, call the `GenerateCrc32Hash` function and pass the string to it:
```cpp
#include "RESTBL.h"

int main()
{
    ResTableFile RSTB("ResourceSizeTable.Product.121.rsizetable");
    uint32_t Hash = RSTB.GenerateCrc32Hash("Banc/SmallDungeon/Dungeon001_Static.bcett.byml");
    return 0;
}
```

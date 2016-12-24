# hiredis-0.13.3-windows
Porting hiredis-0.13.3 to Windows

Porting is based on [Microsoft/hiredis](https://github.com/Microsoft/hiredis),
which is based on hiredis 0.11.

## Steps

1. Extract hiredis-0.13.3.zip as hiredis-0.13.3-windows/hiredis.
    - Need subdir hiredis to ```#include <hiredis/hiredis.h>```.
2. Merge Microsoft/hiredis master to hiredis/hiredis v0.13.3
    1. Fork hiredis/hiredis to jinq0123/hiredis
    2. Branch from tag v0.13.3 to Branch_v0.13.3
    3. Merge Microsoft/hiredis master resolving many conflicts.
        - Keep sds.* which support win32.
    4. Other (optional)
        - Replace
            + long long -> PORT_LONGLONG
            + unsigned long -> PORT_ULONG
            + long -> PORT_LONG
        - Delete zmalloc.h
        _ snprintf
    5. Export Branch_v0.13.3 and replace hiredis-0.13.3-windows/hiredis.

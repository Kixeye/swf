# Kixeye changes on top of swf 3.4.0

Branch `upgrade/swf-3.4.0` starts at upstream swf `3.4.0` (tag `upgrade-base-swf-3.4.0`).
Fork of https://github.com/openfl/swf. Drop this fork once upstream releases the fix below.

| Change | Why |
|---|---|
| `ShapeBitmapExporter`: adds back the EndFill after a cleared line style before checking for bitmap-only shapes | swf 3.4.0 fixed `SWFShape` writing an extra EndFill at the start of shapes, but the bitmap check still expects it, so it never matched. Bitmap-only shapes were then exported as bitmap-fill shapes instead of Bitmaps (1,086 symbols in Battle Pirates), which draws each copy to its own canvas and texture |

`run.n` is not in git: build it with `haxe rebuild.hxml`.

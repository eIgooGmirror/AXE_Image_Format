# AXE (Animated piXel Exchange) Specs

Bytes 0-2: Magic number (415845) AXE in ASCII
Byte 3: Loop Or Not (0=No, 1=Yes)
Bytes 4-32: Zeroes Intended To Take Up Space

# Chunk MAIN (4D41494E): Data for the main canvas
Bytes 0-3: Number Of Sprites

Bytes 4-7: Number Of Frames

Bytes 8-10: Background Color (24 Bit HEX RGB)

Bytes 11-14: Overall X Length

Bytes 15-18: Overall Y Length

Bytes 19-22: Full Image Size

# Chunk SPRT (53505254): Data for a specific sprite
Bytes 0-3: Sprite Number

Bytes 4-8: X Length

Bytes 9-12: Y Length

Byte 13: Compression (0=None, 1=RLE)

Byte 14: Image Bits (4, 8, 24, 32)

Byte 15: Sprite Size (header+color data)

Byte 16: Image Color Data Size

Color Data

# Chunk PLTE (504C5445): Palette Data
Bytes 0-3: Sprite Number

Bytes 4-5: Palette Bits (8= 256 Colors, 4=16 Colors)

Pallette Data (Stored In 32 Bit RGBA Format)

# Chunk FRME (46524D45): Frame Data

Byte Sequence (Repeated For Each Sprite):

Bytes 0-3: Sprite Number

Bytes 4-8: Sprite X Offset

Bytes 9-12: Sprite Y Offset

MODS

# Chunk MODS (4D4F4453): Graphic Translations, Rotations

Bytes 0-3: Sprite Size (Divided By 65536)

Bytes 4-5: Sprite Direction (0-359)

# Chunk SIZE (53495A45): The Size Of The Image (If nonexistent, it’s assumed to be 1)

Bytes 0-1: The Pixel Size

# Chunk FNSH (464E5348): The End Of The Image (All Data Beyond That Is Optional)

Bytes 0-719: Author Comments (720 Bytes To Fit Anything The Author Wants To Say About The Image In ASCII)

Bytes 720-849: The Name Of The File

Bytes 850-950: The Author’s Name

Bytes 900-901: Time Spent Creating The File (Optional)

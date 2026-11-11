Header - 0x14
0x0 - Magic of four bytes, 'ROLM'
0x4 - Endianess 2 bytes (BIG ENDIAN is default) 0x10, 0x50 = big endian, 0x50, 0x10 is little endian.
0x6 - Version 2 bytes (u16) 1.0 is 10
0x8 - Face count 4 bytes (u32)
0xC - Offset to section vert (relative to here)
0x10 - Offset to section Indicies (relative)


Vertex Struct - 0x24
0x0 + 0xC - Position data, three floats
0xC + 0xC - Normal data, three floats
0x18 + 0x4 - Color data, one u32 value (convert to color)
0x1C + 0x8 - Tex Coord data, two floats

Vertices_size = (0x24 * (Face count * 3))

0x14 - Section Header 'VERT'
0x18 + Vertices_size  - Vertices


Indice_pos = 0x18 + Vertices_size 

Face data:
0x0 - vertex 1, u32
0x4 - vertex 2, u32
0x8 - vertex 3, u32

Indice_pos - 'FACE' Section Header
Indice_pos + 0x4 + (Face count * Face data size) - Face data
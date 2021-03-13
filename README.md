# RayZ

#### Schema
The following structure is repeated until EOF. There is **no** length prefix, so you have to read to EOF to read all the mappings.
| type | description |
|------|-------------|
| unsigned varint32 | r12 block string ID length |
| byte[] | r12 block string ID |
| little-endian int16 | r12 block metadata |
| TAG_Compound (varint format) | current version NBT blockstate corresponding to the given r12 block |

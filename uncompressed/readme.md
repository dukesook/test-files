# Uncompressed MP4 Files

## Documentation

- See [ISO/IEC 23001-17:2024](https://www.iso.org/standard/82528.html)

```C++
// The 'uncC' Box
aligned(8) class UncompressedFrameConfigBox extends FullBox('uncC', version, 0) {
  unsigned int(32) profile;
  if (version==1) {
  }
  else if (version==0) {
    unsigned int(32) component_count;
    {
      unsigned int(16) component_index;
      unsigned int(8) component_bit_depth_minus_one;
      unsigned int(8) component_format;
      unsigned int(8) component_align_size;
    } [component_count];
    unsigned int(8) sampling_type;
    unsigned int(8) interleave_type;
    unsigned int(8) block_size;
    bit(1) components_little_endian;
    bit(1) block_pad_lsb;
    bit(1) block_little_endian;
    bit(1) block_reversed;
    bit(1) pad_unknown;
    bit(3) reserved = 0;
    unsigned int(32) pixel_size;
    unsigned int(32) row_align_size;
    unsigned int(32) tile_align_size;
    unsigned int(32) num_tile_cols_minus_one;
    unsigned int(32) num_tile_rows_minus_one;
  }
}
```

```C++
// The 'cmpd' Box
aligned(8) class ComponentDefinitionBox extends Box('cmpd') {
  unsigned int(32) component_count;
  {
    unsigned int(16) component_type;
    if (component_type>=0x8000) {
      utf8string component_type_uri;
    }
  } [component_count];
}
```

## gpac_64x64.mp4

- Uncompressed MP4 test file, generated using GPAC's [uncvg](https://wiki.gpac.io/Filters/uncvg/#options).
- `$ gpac uncvg:vsize=64x64 -o out.mp4`

# Image Pyramid

## Draft 'pymd' Definition

```C++
aligned(8) class ImagePyramidEntityGroup
extends EntityToGroupBox ('pymd', version = 0, flags = 0) {
  unsigned int(16) tile_size_x;
  unsigned int(16) tile_size_y;
  for(i=0; i<num_entities_in_group;i++) {
    unsigned int(16) layer_binning;
    unsigned int(16) tiles_in_layer_row_minus1;
    unsigned int(16) tiles_in_layer_column_minus1;
 }
}
```

## Feedback on pymd box

I believe most of the variables this definition are redundant and should be removed for simplification.
See this [issue](https://github.com/MPEGGroup/FileFormat/issues/100) for more details.

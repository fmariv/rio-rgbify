# rio-rgbify
Encode arbitrary bit depth rasters in pseudo base-256 as RGB.

As it seems that the project is nearly abandoned, I'm commited to maintain and power rio-rgbify with the PR and improvements that have been made by the awesome open source community. That's why I say it's the usual rio-rgbify, but with steroids 💪

## Installation

```
git clone git@github.com:fmariv/rio-rgbify.git

cd rio-rgbify

pip install -e '.[test]'

```

## CLI usage

- Input can be any raster readable by `rasterio`
- Output can be any raster format writable by `rasterio` OR
- To create tiles _directly_ from data (recommended), output to an `.mbtiles`

```
Usage: rio rgbify [OPTIONS] SRC_PATH DST_PATH

Options:
  -b, --base-val FLOAT   The base value of which to base the output encoding
                         on [DEFAULT=0]
  -i, --interval FLOAT   Describes the precision of the output, by
                         incrementing interval [DEFAULT=1]
  -r, --round-digits     Less significants encoded bits to be set
                         to 0. Round the values, but have better
                         images compression [DEFAULT=0]
  --bidx INTEGER         Band to encode [DEFAULT=1]
  --max-z INTEGER        Maximum zoom to tile (.mbtiles output only)
  --bounding-tile TEXT   Bounding tile '[{x}, {y}, {z}]' to limit output tiles
                         (.mbtiles output only)
  --min-z INTEGER        Minimum zoom to tile (.mbtiles output only)
  --format [png|webp]    Output tile format (.mbtiles output only)
  -j, --workers INTEGER  Workers to run [DEFAULT=4]
  -v, --verbose
  --co NAME=VALUE        Driver specific creation options.See the
                         documentation for the selected output driver for more
                         information.
  --help                 Show this message and exit.
```

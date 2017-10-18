# ImageMagick

convert imagers with ImageMagick


## downsample

convert <infile> -filter Lanczos -sampling-factor 1x1 -quality 90 -resize <geom> <outfile>


## upscale

convert <infile> -filter triangle -unsharp 0x0.75+0.75+0.008 -resize <geom> <outfile>

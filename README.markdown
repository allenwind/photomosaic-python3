# Requirements
- [Python Imaging Library][PIL]

Origin from https://github.com/john2x/photomosaic
I make it supports Python3 and use memory except disk so that effective.


# Usage
## Prepare your image pool
1. Collect a ton of images (2000 is a good number) for your image pool and place them in a directory (e.g. `tiles/`). Make sure they are the same size and w/h ratio\*.
2. Run `$ python3 create_image_pool.py tiles/` to create the tiles database.

\* use `check_images.py` to "weed" out images with different ratios 
    $ python check_images.py tiles_dir desired_width desired_height weeded_tiles_dir
This will put all images not matching `desired_width` and `desired_height` into `weeded_tiles_dir` so you can fix them later on and re-add them into the image pool.  

## Creating the mosaic
After running `create_image_pool.py`, you can now create mosaics.
    $ python photomosaic.py [options] source_image.jpg output_image.jpg tiles_dir


[PIL]: http://www.pythonware.com/products/pil/
[website]: http://john2x.com/projects/photomosaic

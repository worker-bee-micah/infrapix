infrapix-mov
============

converting infragram vid files to NDVI

(Note: check the below ffmpeg commands for accuracy, may need to be modified / corrected)

- first, extract all the frames into a folder:

``` ffmpeg -i inputMovie.avi  -f image2 ./outFolder/image-%04d.png

- then, run the python script to convert to NDVI:

``` python convertMovie.py

(Note: the file paths are currently hard-coded in convertMovie.py; it's now set to export the NDVI images to a folder called 'NDVIFolder')

- then, recombine the extracted frames into a movie:

``` ffmpeg -qscale 5 -r 20 -b 9600 -i ./NDVIFolder/ndvi_image-%04d.png movie.mp4

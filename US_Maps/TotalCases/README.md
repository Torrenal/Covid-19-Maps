# Total Cases

![US Map, Total Cases](../../us-cases-small.png)

Cases are plotting with a quasi-log scale, aiming to not lose detail for any data that is in-range.

The images here plot Cases, and are population normalized. Functionally, what's being rendered is:
 Value = Cases / Population
 
This map is in a 'Draft' state - By all means view it, but take it with a grain of salt - it's literally just been created and  still needs to be reviewed for accuracy.  It's probably OK, but "probably OK" isn't good enough for me.

The raw stills for each date are named us-cases-####.png
There's a single 'us-cases.png' which is an APNG animation of the individual slides.

# Details

 Location: 49.5N to 24N, and 66W to 125.5W.
 
 Projection: Equirectangular Projection.
 
You can view these images by adding them to a KML file with the above coordinates, or by adding them
as an Image Overlay at those locations in Google Maps Pro (These by default assume an equirectangular projection, thus have no issues displaying the images with correct stretching).

## The border
For the time being, an approximate border mask is used, the bulk of it is derived by a naieve algorythm on the fly.  It makes  assumptions about the border based on the data it's processing.  
### Replacing the border mask
The raw output is all in the image, to access it you just need to reset the Alpha channel.  GIMP's Colors->Curves function may suffice for the task.  Once the mask is off, you are free to replace it with your own.

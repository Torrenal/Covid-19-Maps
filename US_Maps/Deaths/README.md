Deaths are plotting with a quasi-log scale, aiming to not lose detail for any data that is in-range.

The images here plot Deaths / Population.

The raw stills for each date are named us-deaths-####.png
There's a single 'us-deaths.png' which is an APNG animation of the individual slides.


# Details

 Location: 49.5N to 24N, and 66W to 125.5W.
 Projection: Equirectangular Projection.
 
You can view these images by adding them to a KML file with the above coordinates, or by adding them
as an Image Overlay at those locations in Google Maps Pro (These by default assume an equirectangular projection, thus have no issues displaying the images with correct stretching).

## The border
For the time being, an approximate border mask is used, the bulk of it is derived by a naieve algorythm on the fly, which makes assumptions about the border based on the data it's processing.  
### Replacing the border mask
The raw output is all in the image, to access it you just need to reset the Alpha channel.  GIMP's Colors->Curves function may suffice for the task.  Once the mask is off, you are free to replace it with your own.

Legend (to be created)
Color coding is black-red-yellow-???-???, with black being no cases and full-red (0xFF0000) being 1/4 of the way the up the full scale.  The halfway point is full yellow (0xFFFF00)  The top half of the scale is presently uncolored (no data currently being rendered reaches it), but the scale will be extended if the need arises.

## Reading the map
The map is created from county-level data, so don't try looking for detail smaller than counties.  The strength of this map is that it's easier to grasp what's occurring over time with an animation than with most other maps that I've seen plotting this data.  

## Scale Math
Get the deathsRate into the format of deaths/saturationCount.
Saturation Count is the 'estimated total deaths if everyone gets sick', and for
our purposes here a fatality rate of 1% is assumed, so we have effectively:
 DeathRate = deaths/(Population/100)
Then we apply log scaling to the calculated DeathRate.  If it's below 0.5, we take the log deathRate and normalize between 0 and .5
If it's over .5, we subtract it from 1, take the log, and normalize between .5 and 1.

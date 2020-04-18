Deaths are plotting with a quasi-log scale, aiming to not lose detail for any data that is in-range.

The images here plot Deaths / Population.

The raw stills for each date are named us-deaths-####.png
There's a single 'us-deaths.png' which is an APNG animation of the individual slides.


# Details

 Location: 49.5N to 24N, and 66W to 125.5W.
 Projection: Equirectangular Projection.
 
You can view these images by adding them to a KML file with the above coordinates, or by adding them
as an Image Overlay at those locations in Google Maps Pro (These assume an equirectangular projection).

Borders are currently autodetected and "outside" regions are rendered as transparent.  This may change based on needs.

Legend (to be created)
Color coding is black to red, with black being no cases and full-red (0xFF0000) being 1/4 of the way the up the scale.  The top of the scale is presently uncolored (no data currently being rendered reaches it). Future work may require extending the scale
into other colors (TBD).

## Scale Math
Get the deathsRate into the format of deaths/saturationCount.
Saturation Count is the 'estimated total deaths if everyone gets sick', and for
our purposes here a fatality rate of 1% is assumed, so we have effectively:
 DeathRate = deaths/(Population/100)
Then we apply log scaling to the calculated DeathRate.  If it's below 0.5, we take the log deathRate and normalize between 0 and .5
If it's over .5, we subtract it from 1, take the log, and normalize between .5 and 1.




Deaths are plotting with a quasi-log scale, aiming to not lose detail for any data that is in-range.

The images here plot Deaths over Population.  Functionally, what's being rendered is:
 Value = Deaths * 100 / Population

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

Legend (formal version pending)
Color coding is presently based off of a HSB scale, and may be subject to future changes.  The file 'legendTest.png' contains the full legend. For this chart, it's the bottom scale and read left to right, as 'low to high'.  This is provided in case you want to remap to your own color scheme)

## Reading the map
The map is created from county-level data, so don't try looking for detail smaller than counties.  The strength of this map is that it's easier to grasp what's occurring over time with an animation than with most other maps that I've seen plotting this same data - it's fitting the data to natural curves rather than rigid shapes, and those curves move over time in response to changes in the data.

## Scale Math
The scale has a log component to it so as not to lose the ability to reflect meaningful detail at any scale.
Start by calculating the raw value of Deaths * 100 / Population.

This yields a number (that should be) in the range of 0 to 1.

If the value is between 0 and 0.5, use Log10(0.5)/2/Log10(value)
If the value is between 0.5 and 1, use the 1- Log10(0.5)/2/Log10(1-value)

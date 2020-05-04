# Growth Rate plots

![US Map, Growth Rate](../../us-doubling-rates-deaths-small.png)

This plot represents the current growth/decline of Covid related deaths across the country.  Unlike the other maps, these are not population normalized.

These plots are of the format: 
Old Deaths = total deaths 7 days ago - total deaths 14 days ago.
Recent Deaths = total deaths today - total deaths 7 days ago.

If Recent Deaths > Old Deaths:
   Doubling period = Log(2) / Log(RecentDeaths/OldDeaths) * 7

If Recent Deaths < Old Deaths:
   Halving period = Log(2) / Log(OldDeaths/ RecentDeaths) * 7

If we're halving (rates are decling): Plot in green.  If we're doubling, Plot in red.

The brightest colors are given to calculated rates of better than every 10 days (so if it doubles in 8 days, bright red.  Halves in y?>  bright green).  There's a middle tone for both red and green, which is for doubling/havling rates in the 10-30 day range, and the darker colors are for anything slower than 30 days - which for our purposes makes it essentially flat.

Bright colors do not mean things are very good or very bad, they mean things are moving in that direction quickly.

# Details

 Location: 49.5N to 24N, and 66W to 125.5W.
 
 Projection: Equirectangular Projection.
 
You can view these images by adding them to a KML file with the above coordinates, or by adding them
as an Image Overlay at those locations in Google Maps Pro (These by default assume an equirectangular projection, thus have no issues displaying the images with correct stretching).

## The border
For the time being, an approximate border mask is used, the bulk of it is derived by a naieve algorythm on the fly.  It makes  assumptions about the border based on the data it's processing.  
### Replacing the border mask
The raw output is all in the image, to access it you just need to reset the Alpha channel.  GIMP's Colors->Curves function may suffice for the task.  Once the mask is off, you are free to replace it with your own.

## Notes
* I've had to adjust how I weight the data by distance from how the other plots do it.  While I think it's mostly a fair outcome, I'm not happy with how New York City presents, essentially as a splotch over it's region.  I've not looked more closely at that, but if it's like past things I've examined, its a good chance that's just what the data is doing.  Review warranted.
* The source data has death counts that go "backwards".  ie: There were a grand total of 30 people killed to date as of last week, and as of today that total has gone down(?!?) to 14.  Either 16 people came back to life, or there's something off in the data.  Occurrences of people "returning-to-life" are filtered out of this plot.
* Theres a 'previous 7 days' plot and a 'previous 3 days' plot.  Some people are used to seeing things that sumarize 3-day periods, and 7 day periods don't have artifacts from including/excluding different days of the week from one plot to the next.


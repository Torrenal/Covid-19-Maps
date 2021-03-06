# Growth Rate plots

![US Map, Growth Rate](../../us-doubling-rates-cases-small.png)

This plot represents the current growth/decline of Covid related cases across the country.  Unlike the other maps, these are not population normalized.

These plots are of the format: 
Old Cases = total cases 7 days ago - total cases 14 days ago.
Recent cases = total cases today - total cases 7 days ago.

If Recent Cases > Old Cases:
   Doubling period = Log(2) / Log(RecentDeaths/OldDeaths) * 7

If Recent Cases < Old Cases:
   Halving period = Log(2) / Log(OldDeaths/ RecentDeaths) * 7

If we're halving (rates are decling): Plot in green.  If we're doubling, Plot in red.

The brightest colors are given to calculated rates of better than every 10 days (so if it doubles in 8 days, bright red.  Halves in y?>  bright green).  There's a middle tone for both red and green, which is for doubling/havling rates in the 10-30 day range, and the darker colors are for anything slower than 30 days - which for our purposes makes it essentially flat.

Bright colors do not mean things are very good or very bad, they mean things are moving in that direction quickly.  For how good or bad things are at a given spot, you want to be looking at the new cases maps.

# Details

 Location: 49.5N to 24N, and 66W to 125.5W.
 
 Projection: Equirectangular Projection.
 
You can view these images by adding them to a KML file with the above coordinates, or by adding them
as an Image Overlay at those locations in Google Maps Pro (These by default assume an equirectangular projection, thus have no issues displaying the images with correct stretching).

### Replacing the border mask
The raw output is all in the image, to access it you just need to reset the Alpha channel.  GIMP's Colors->Curves function may suffice for the task.  Once the mask is off, you are free to replace it with your own.

## Notes
* I've had to adjust how I weight the data by distance from how the other plots do it.  While I think it's mostly a fair outcome, I'm not happy with how New York City presents, essentially as a splotch over it's region.  I've not looked more closely at that, but if it's like past things I've examined, its a good chance that's just what the data is doing.  Review warranted.
* The source data has death counts that go "backwards".  ie: There were a grand total of 30 people killed to date as of last week, and as of today that total has gone down(?!?) to 14.  Either 16 people came back to life, or there's something off in the data.  Occurrences of total counts going down are filtered out of this plot.

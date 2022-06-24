## How to export Diabotical maps
_(props will be ignored, only works for blocks)_
1.   `/export themap` will give you an `obj` file _(outputs to install folder, not to /homedir)_
2.   Import the file to blender
3.   Add `Weld` modifier set to `1m`, and apply it  
4.   Add `Decimate` modifier, set to `Planar : 45deg : UV`, and apply it  
5.   Import the resulting model to Source or Q3 engine  

## Exporting as .map
It's possible to export as `.map`, but it takes a long time for the exporting of big maps, even with geometry simplified. There is an addon for it in quBit's blender trello board  
I think it might be better to export as model and use autoclip, since geometry is simple enough.   
But haven't tested that process yet.  

For reference:  
`Microaltar` exported to brushes no problm, but it was 12mb and took half an hour.  
Tried the same with `RGB`, which is 400mb... and its been 10h and it hasn't finished.  
So not convinced it will work well with this workflow when the map is decently big, need to find better methods  

The map exports as thin brushes when you select "faces" in the export tab.   
They turn into pyramidal shapes. All normal behavior.  
They work well ingame since they are all very flat and aligned to the grid.  
_This triangulation is what takes so long to process, which I believe is the same process done by model autoclip in Q3_  

## Brushes, instead of triangulated faces
There is the option to export as brushes (change it during export), but you need to do some cleanup in blender before exporting for that to work. Otherwise the whole map turns into a box.

1. Click a few faces that are part of the same brush
2. Press `P` to separate selection
3. The exporter will give you a perfectly normal brush (not triangulated) from those shapes

With this method:  
: 3 planes turn into a box brush  
: 2 planes turn into a pyramidal brush, with an angled face (ramp) filling the back spaces  
Its doable, and faster than cleaning up in radiant, but it takes a bit of getting used to the process and Blender.  

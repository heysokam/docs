## How to export Diabotical maps
**Block-based maps**
1.   `/export themap` will give you an `obj` file _(outputs to /gamedir, not /homedir)_
2.   Import the file to blender
3.   Add `Weld` modifier set to `1m`, and apply it  
4.   Add `Decimate` modifier, set to `Planar : 45deg : UV`, and apply it  
5.   Export the resulting model to Source or Q3 engine  

## Scale (dbt to q3df/mmdf)
1. Scale Z by `1.1`  
2. Scale X and Y by `1.2`  

This makes 40u high blocks into 44u, which is max skimmable.  
And everything else 48u, which is the scale equivalent (roughly) from dbt to defrag.

## Exporting as .map
It's possible to export as `.map`, but it takes a long time for the exporting of big maps, even with geometry simplified.  
[.map exporter](https://trello.com/c/6Zml1gSu/149-quake-3-map-brush-exporter-addon-for-blender)  
I think it might be better to export as model and use autoclip, since geometry is simple enough.   
But haven't tested that process yet. _(see exporting as q3-model section)_  

For reference:  
`Microaltar` exported to brushes no problem, but it was 12mb and took half an hour.  
Tried the same with `RGB`, which is 400mb... and after 12h and it still hadn't finished.  
So not convinced it will work well with this workflow when the map is decently big, need to find better methods.  

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


## Prop-based maps
1.   `/find *` in console
2.   `/export_selection themap` will give you an `obj` file _(outputs to /gamedir, not /homedir)_
3.   Import the file to blender
4.   Export the resulting model to Source or Q3 engine  

Exporting invis props to `.map` as brushes works perfectly, without any issues, if there is nothing else in the map.  
And they are converted to standard `.map` brushes, without irregular shapes.  
_(tested: boxes and cylinders, both invis and opaque)_  

_Note:_  
_Some complex props break the exporter very heavily._  
_You will need to experiment removing different props, until the geometry stops getting borked on export._  

## Exporting as Q3 model
_TBD. Related info:_  
[about models](https://trello.com/c/sE516Emm/161-about-models)  
[md3-exporter](https://trello.com/c/aMEbgAXC/151-bsp-lightmapper-bake-lightmaps-in-blender-%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80-md3-exporter-with-custom-normals%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80%E2%A0%80-bsp-importer)  

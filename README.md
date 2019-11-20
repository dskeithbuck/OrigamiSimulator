# OrigamiSimulator

Live demo at [origamisimulator.org](https://origamisimulator.org/)  

![Unfolding paper crane.](assets/doc/crane.gif)

This app allows you to simulate how any origami crease pattern will fold. It may look a little different from what you typically think of as "origami" - rather than folding paper in a set of sequential steps, this simulation attempts to fold every crease simultaneously. It does this by iteratively solving for small displacements in the geometry of an initially flat sheet due to forces exerted by creases. You can read more about it in our paper:

* [Fast, Interactive Origami Simulation using GPU Computation](http://erikdemaine.org/papers/OrigamiSimulator_Origami7/) by Amanda Ghassaei, Erik Demaine, and Neil Gershenfeld (7OSME)

All simulation methods were written from scratch and are executed in parallel in several GPU fragment shaders for fast performance. The solver extends work from the following sources:

* [Origami Folding: A Structural Engineering Approach](http://www2.eng.cam.ac.uk/~sdg/preprint/5OSME.pdf) by Mark Schenk and Simon D. Guest
* [Freeform Variations of Origami](http://www.tsg.ne.jp/TT/cg/TachiFreeformOrigami2010.pdf) by Tomohiro Tachi  
    

## Instructions: 
  
![UI Demo](assets/doc/demoui.gif)  

* Slide the **Fold Percent** slider to control the degree of folding of the pattern (100% is fully folded, 0% is unfolded, and -100% is fully folded with the opposite mountain/valley assignments).
* Drag to rotate the model, scroll to zoom.
* Import other patterns under the **Examples** menu.
* Upload your own crease patterns in SVG or [FOLD](https://github.com/edemaine/fold) formats, following the instructions under **File > File Import Tips**.
* Export FOLD files or 3D models ( STL or OBJ ) of the folded state of your design ( **File > Save Simulation as...** ).  
![](assets/doc/strain.jpg)
* Visualize the internal strain of the origami as it folds using the **Strain Visualization** in the left menu.  
![](assets/doc/huffmanvr.jpg)
* If you are working from a computer connected to a Vive, follow the instructions near the **VR** menu to use this app in an interactive virtual reality mode.
  
## External Libraries:
  
* All rendering and 3D interaction done with [three.js](https://threejs.org/)
* [path-data-polyfill](https://www.npmjs.com/package/path-data-polyfill) helps with SVG path parsing
* [FOLD](https://github.com/edemaine/fold) is used as the internal data structure, methods from the [FOLD API](https://github.com/edemaine/fold/blob/master/doc/api.md) used for SVG parsing
* Arbitrary polygonal faces of imported geometry are triangulated using the [Earcut Library](https://github.com/mapbox/earcut)
* GIF and WebM video export uses [CCapture](https://github.com/spite/ccapture.js/)
* Portability to multiple VR controllers by [THREE.VRController.js](https://github.com/stewdio/THREE.VRController)
* VR GUI by [dat.guiVR](https://github.com/dataarts/dat.guiVR)
* [numeric.js](http://www.numericjs.com/) for linear algebra operations
* [FileSaver](https://github.com/eligrey/FileSaver.js/) for client-side file saving
* [jQuery](https://jquery.com/), [Bootstrap](http://getbootstrap.com/), and the [Flat UI theme](http://designmodo.github.io/Flat-UI/) used to build the GUI
  
Built by [Amanda Ghassaei](http://www.amandaghassaei.com/) as a final project for [Geometric Folding Algorithms](http://courses.csail.mit.edu/6.849/spring17/). Code available on [Github](https://github.com/amandaghassaei/OrigamiSimulator). If you have interesting crease patterns that would make good demo files, please send them to me (Amanda) so I can add them to the **Examples** menu. My email address is on my website. Thanks!  
  
You can find additional information in [our 7OSME paper](http://erikdemaine.org/papers/OrigamiSimulator_Origami7/) and [this website](http://www.amandaghassaei.com/projects/origami_simulator/).

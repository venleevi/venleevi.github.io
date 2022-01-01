---
layout: single
toc: false
classes: wide
last_modified_at: 2022-1-1
title: 3D visualization of astronomical data using Pyvista
excerpt: ""
header:
   image: /assets/images/pencil-code/streamline-header-image.png
   teaser: /assets/images/pencil-code/streamline-header-image.png
   overlay_filter: 0.4
gallery:
  - url: /assets/images/pencil-code/cartesian_moving_isovalue.gif
    image_path: /assets/images/pencil-code/cartesian_moving_isovalue.gif
    alt: "placeholder image 1"
    title: "Cartesian moving isovalue plot"
  - url: /assets/images/pencil-code/spherical_moving_isovalue.gif
    image_path: /assets/images/pencil-code/spherical_moving_isovalue.gif
    alt: "Spherical moving isovalue"
    title: "Spherical moving isovalue plot"
  - url: /assets/images/pencil-code/volume-streamlines-culling-back.png
    image_path: /assets/images/pencil-code/volume-streamlines-culling-back.png 
    alt: "Volume streamlines in cartesian coordinates. Culling is applied to the surface data such that only the back surfaces are shown."
  - url: /assets/images/pencil-code/spherical-surface-streamlines.png
    image_path: /assets/images/pencil-code/spherical-surface-streamlines.png 
    alt: "Spherical surface streamlines"
  - url: /assets/images/pencil-code/overly-zoomed-in-streamlines.png
    image_path: /assets/images/pencil-code/overly-zoomed-in-streamlines.png
    alt: "A very zoomed in visualization a vector field."
---


**NOTE!** I'm still writing this post so hopefully nobody sees this :)
{: .notice--danger}

<img src="/assets/images/pencil-code/cartesian-box-snapshot.png" align="right" width="30%">

Aim of this work was to **create visualizations for 3D astronomical data**. This includes both scalar and vector fields. The data itself consisted of either **volumetric data or 4x 2D slices from a volume**. These four slices are along each of the axes of the coordinate system (with one extra slice). In the case of cartesian coordinates these slices could then be assembled into a box for visualization purposes (shown on the right).

The astronomical simulation data itself comes from the [pencil-code](https://github.com/pencil-code/pencil-code) simulations and was visualized using [Pyvista](https://docs.pyvista.org). Most of the visualizations were run locally though longer movies were generated on the CSC Puhti supercomputing cluster. The developed code itself can also be found from the 

Some of the implemented features include:

* Visualizations in different coordinate systems: cartesian / spherical / cylinder

* Visualization of both 

* Different methods of vector field visualization: streamlines/vector arrows, colormapping these and scaling according to vector magnitude

Some sample nice sample visualizations are shown in the next gallery but do note **that most of these are just nice visuals but don not convey actual information that well**. For more informatic visuals see the *Extras* section first video for video showing the time evolution of chosen scalar and vector fields.

{% include gallery caption="Some sample visualizations I produced." %}

---

# Extras: video demos

Here are a few example demo videos I had generated. Unfortunately the quality seems bad after uploading and in addition the starting aspect ratio is a bit awkward (something to fix?). Note that for the latter two of the videos the playback speed has been doubled or tripled.

* First video shows scalar values on four 2D slices assembled to a box for visualization purposes. On the left the vector field (shown by the streamlines) is velocity and on the right the magnetic field.

<iframe width="560" height="315" src="https://www.youtube.com/embed/GqYbyNtQhws" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

* Second video shows a volume rendering of a scalar value (rho = density) and a vector velocity field visualized again using streamlines. For testing purposes one can adjust the opacity of the volume rendering of the scalars.

<iframe width="560" height="315" src="https://www.youtube.com/embed/-w8EP2D9C-g" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

* And finally the third shows a slice widget where one can control the location and orientation of a slicing plane with the volume data. With this one can see more clearly the behaviour of the scalar and vector fields inside a volume without other data obstructing the view.

<iframe width="560" height="315" src="https://www.youtube.com/embed/cWRE4LxPL-0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

---

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
    alt: "Cartesian moving isovalue"
    title: "Cartesian moving isovalue plot"
  - url: /assets/images/pencil-code/spherical_moving_isovalue.gif
    image_path: /assets/images/pencil-code/spherical_moving_isovalue.gif
    alt: "Spherical moving isovalue"
    title: "Spherical moving isovalue plot"
  - url: /assets/images/pencil-code/volume-streamlines-culling-back.png
    image_path: /assets/images/pencil-code/volume-streamlines-culling-back.png 
    alt: "volume streamlines"
    title: "Volume streamlines in cartesian coordinates. Culling is applied to the surface data such that only the back surfaces are shown."
  - url: /assets/images/pencil-code/spherical-surface-streamlines.png
    image_path: /assets/images/pencil-code/spherical-surface-streamlines.png 
    alt: "spherical streamlines"
    title: "Spherical surface streamlines"
  - url: /assets/images/pencil-code/overly-zoomed-in-streamlines.png
    image_path: /assets/images/pencil-code/overly-zoomed-in-streamlines.png
    alt: "Zoomed in streamlines"
    title: "A very zoomed in visualization of a vector field."
---


**NOTE!** I'm still writing this post so hopefully nobody sees this :)
{: .notice--danger}

<img src="/assets/images/pencil-code/cartesian-box-snapshot.png" align="right" width="30%">

This project was done during 5.2021-9.2021 at the Department of Computer Scince at Aalto University in the *Astroinformatics* group. 

Aim of this work was to **create visualizations for 3D astronomical data**. This includes both scalar and vector fields. The data itself consisted of either **volumetric data or 4x 2D slices from a volume**. These four slices are along each of the axes of the coordinate system (with one extra slice). In the case of cartesian coordinates these slices could then be assembled into a box for visualization purposes (shown on the right).

The astronomical simulation data itself comes from the [pencil-code](https://github.com/pencil-code/pencil-code) simulations and was visualized using [Pyvista](https://docs.pyvista.org). Most of the visualizations were run locally though longer movies were generated on the CSC Puhti supercomputing cluster. The developed code itself can also be found from the 

Some of the implemented features include:

* Visualizations in different coordinate systems: cartesian / spherical / cylinder

* Creating videos from time-series scalar and vector field data (see video demos below, first video) 

* Different methods of vector field visualization: streamlines / vector arrows, colormapping these and scaling according to vector magnitude

* Other visualization methods including volume rendering of scalar volumetric data, plotting isovalues and different interactive methods of data visualization (e.g. an interactively controlled slicing plane).

Some sample nice sample visualizations are shown in the next gallery. The two first isovalue visualizations are gifs showing a moving range of isosurfaces of a scalar field. **The images / gifs might take a moment to load fully.**

{% include gallery caption="Sample visualizations." %}

---

# Video demos

Here are a few example demo videos I had generated using the developed plotting utilities. Unfortunately the quality seems bad after uploading and in addition the starting aspect ratio is a bit awkward (something to fix?). Note that for the latter two of the videos the playback speed has been doubled or tripled.

* First video shows the **time-evolution of velocity** (*left*) **and magnetic fields** (*right*). These are visualized using streamlines - colormap and stream radius scaling shows the magnitude of the field at a point. Below streamlines the colormap shows the logarithmic density $\log\rho$. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/GqYbyNtQhws" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

* Second video shows a **volume rendering of scalar volumetric data** (density). In addition the vector field (velocity) is shown by the streamlines in the volume. This is an interactive window that is opened by the plotting script and the slider controls the opacity of the volume rendering.

<iframe width="560" height="315" src="https://www.youtube.com/embed/-w8EP2D9C-g" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

* And finally the third video shows an **interactive slice widget*** where one can control the location and orientation of a slicing plane. With this one can see more clearly the behaviour of the scalar and vector fields inside a volume without other data obstructing the view.

<iframe width="560" height="315" src="https://www.youtube.com/embed/cWRE4LxPL-0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

---

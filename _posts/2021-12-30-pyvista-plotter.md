---
layout: single
toc: false
classes: wide
last_modified_at: 2021-12-30
title: 3D visualization using Pyvista
excerpt: ""
header:
   overlay_image: /assets/images/pencil-code/streamline-header-image.png
   overlay_filter: 0.4
---


**NOTE!** I'm still writing this post so hopefully nobody sees this :)
{: .notice--danger}


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

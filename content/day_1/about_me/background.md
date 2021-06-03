+++
title = "Background"
weight = 5
+++

My background is in nuclear engineering, specifically radiation
instrumentation --- devices to measure and image of sources of ionizing
radiation.
The type of 3D radiation imaging that I studied has applications in
environmental monitoring:

{{< figure
    src=/images/fukushima_parkinglot_summary_img.png
    title="3D Radiation Mapping in Fukushima."
    caption="**Right:** Aerial view of measurement area. **Left:** 3D gamma-ray image reconstruction --- Red line = path of imager through the scene, B/W dots = 3D point cloud model of the scene, Heatmap = image reconstruction; color scale corresponds to relative reconstructed intensity."
>}}

As well as medical imaging:

{{< figure
    src=/images/CCI2_nearfield_linesource.png
    title="Near-field Compton gamma-ray imaging"
    caption="Demonstration of Compton imaging for applications in small animal molecular imaging. **Left:** A Cs-137 calibration source in the shape of a thin rod mounted on a rotating stage. **Right:** Three projections of reconstructed image from a tomographic measurement."
>}}

This research was entirely made possible by **open-source software**.
Specifically, my colleagues and I relied heavily on various open-source
packages like [rgbdslam](https://github.com/felixendres/rgbdslam_v2) and
[Google Cartographer](https://google-cartographer.readthedocs.io/en/latest/)
to explore integrating our radiation imaging hardware with real-time SLAM
algorithms.

The second component that was instrumental in my research was scientific
Python software!

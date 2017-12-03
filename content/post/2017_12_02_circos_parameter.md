---
title: "circos parameter"
date: 2017-12-02
---

This blog is a reminder of how to set parameters of [Circos](http://circos.ca/)

heatmap tutorial is at [http://circos.ca/documentation/tutorials/2d_tracks/heat_maps/lesson](http://circos.ca/documentation/tutorials/2d_tracks/heat_maps/lesson)

1. control the heatmap position (r1 and r0)

```shell
#conf file
<plot>
file             = try_heatmap.txt
stroke_thickness = 1
min              = 30
max              = 40
r1    = 0.89r
r0    = 0.88r
</plot>
```

stroke_thickness = 0 should be set, otherwise the heatmap will be all black

2. control heatmap color
```shell
color = XX,YY,ZZ
```

3. control space
```shell
#./ideogram.conf file
<pairwise Chr17 Chr01>
spacing = 25u
</pairwise>
```

4. control font and chr size
```shell
#myetc/ideogram.conf file
# thickness and color of ideograms
thickness        = 5p#25p
label_size     = 26#36
```

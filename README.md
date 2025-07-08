# Quickstart

### Drawing a structure

Utilize the `sequence` and `dot_bracket` URL parameters
to draw a structure specified in dot-bracket notation.

For example, the two hairpin structure...

```
AAGGGGAAAACCCCAAGGGGAAAACCCCAA
..((((....))))..((((....))))..
```

...is drawn by the following URL.

```
https://code.rnacanvas.app?sequence=AAGGGGAAAACCCCAAGGGGAAAACCCCAA&dot_bracket=..((((....))))..((((....))))..
```

### Coloring bases according to data

Bases can be given colored outlines according to data
(e.g., base-pair probability data, positional entropy data)
by utilizing the `data` URL parameter.

For example, suppose the following structure...

```
AGAGUAGCAUUCUGCUUUAGACUGUUAACUUUAUGAACCACGCGUGUCACGUGGGGAGAGUUAACAGCGCCC
(((((((....)))))))...(((((((((((.....(((((.......)))))..))))))))))).....
```

...has the following positional entropy data.

```
0.911,0.323,0.159,0.120,0.116,0.161,0.378,0.090,0.077,0.017,0.024,0.351,0.170,0.121,0.115,0.158,0.316,0.929,0.007,0.007,0.007,0.110,0.026,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.109,0.507,-0.000,-0.000,0.000,0.000,0.000,0.911,0.924,0.710,0.762,0.838,0.711,0.712,0.632,0.001,0.000,-0.000,0.632,0.832,0.713,0.717,0.742,0.896,0.881,0.500,0.495,0.109,0.027,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.110,0.001,0.005,0.005,-0.000,-0.000
```

(Each comma-separated value represents the positional entropy of a single residue in the structure.)

This structure is drawn by the following URL
(giving each base a colored outline according to its positional entropy value).

```
https://code.rnacanvas.app?sequence=AGAGUAGCAUUCUGCUUUAGACUGUUAACUUUAUGAACCACGCGUGUCACGUGGGGAGAGUUAACAGCGCCC&dot_bracket=(((((((....)))))))...(((((((((((.....(((((.......)))))..))))))))))).....&data=0.911,0.323,0.159,0.120,0.116,0.161,0.378,0.090,0.077,0.017,0.024,0.351,0.170,0.121,0.115,0.158,0.316,0.929,0.007,0.007,0.007,0.110,0.026,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.109,0.507,-0.000,-0.000,0.000,0.000,0.000,0.911,0.924,0.710,0.762,0.838,0.711,0.712,0.632,0.001,0.000,-0.000,0.632,0.832,0.713,0.717,0.742,0.896,0.881,0.500,0.495,0.109,0.027,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.110,0.001,0.005,0.005,-0.000,-0.000
```

By default base outlines are colored along a red-to-white gradient.

Base outlines can be colored along a gradient similar to what [RNAfold](http://rna.tbi.univie.ac.at/cgi-bin/RNAWebSuite/RNAfold.cgi) uses
by setting the `color_gradient` URL parameter to `RNAfold`.

```
https://code.rnacanvas.app?sequence=AGAGUAGCAUUCUGCUUUAGACUGUUAACUUUAUGAACCACGCGUGUCACGUGGGGAGAGUUAACAGCGCCC&dot_bracket=(((((((....)))))))...(((((((((((.....(((((.......)))))..))))))))))).....&data=0.911,0.323,0.159,0.120,0.116,0.161,0.378,0.090,0.077,0.017,0.024,0.351,0.170,0.121,0.115,0.158,0.316,0.929,0.007,0.007,0.007,0.110,0.026,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.109,0.507,-0.000,-0.000,0.000,0.000,0.000,0.911,0.924,0.710,0.762,0.838,0.711,0.712,0.632,0.001,0.000,-0.000,0.632,0.832,0.713,0.717,0.742,0.896,0.881,0.500,0.495,0.109,0.027,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.110,0.001,0.005,0.005,-0.000,-0.000&color_gradient=RNAfold
```

By default lower values correspond to the "beginning" of the color gradient
and higher values correspond to the "end" of the color gradient.

Setting the `color_gradient_direction` URL paramter to `reverse` will reverse this.

```
https://code.rnacanvas.app?sequence=AGAGUAGCAUUCUGCUUUAGACUGUUAACUUUAUGAACCACGCGUGUCACGUGGGGAGAGUUAACAGCGCCC&dot_bracket=(((((((....)))))))...(((((((((((.....(((((.......)))))..))))))))))).....&data=0.911,0.323,0.159,0.120,0.116,0.161,0.378,0.090,0.077,0.017,0.024,0.351,0.170,0.121,0.115,0.158,0.316,0.929,0.007,0.007,0.007,0.110,0.026,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.109,0.507,-0.000,-0.000,0.000,0.000,0.000,0.911,0.924,0.710,0.762,0.838,0.711,0.712,0.632,0.001,0.000,-0.000,0.632,0.832,0.713,0.717,0.742,0.896,0.881,0.500,0.495,0.109,0.027,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.110,0.001,0.005,0.005,-0.000,-0.000&color_gradient=RNAfold&color_gradient_direction=reverse
```

Reversing the direction of the color gradient can be useful
when one's data are base-pair probability data
as opposed to positional entropy data.

By default the minimum data value will correspond with the very beginning of the color gradient
and the maximum data value will correspond with the very end of the color gradient.

Setting the `data_min` and `data_max` URL parameters allows one to control where data values fall along the color gradient.

For example, suppose the structure...

```
AGAGUAGCAUUCUGCUUUAGACUGUUAACUUUAUGAACCACGCGUGUCACGUGGGGAGAGUUAACAGCGCCC
(((((((....)))))))...(((((((((((.....(((((.......)))))..))))))))))).....
```

...has the following base-pair probability data.

```
0.689,0.947,0.981,0.986,0.986,0.980,0.938,0.989,0.991,0.998,0.998,0.938,0.980,0.986,0.986,0.981,0.947,0.689,0.999,0.999,0.999,0.986,0.997,1.000,0.999,0.998,0.998,0.999,1.000,0.998,0.987,0.894,1.000,1.000,1.000,1.000,1.000,0.808,0.808,0.806,0.805,0.788,0.805,0.805,0.841,1.000,1.000,1.000,0.841,0.788,0.805,0.806,0.808,0.808,0.813,0.892,0.894,0.987,0.998,1.000,0.999,0.998,0.998,0.999,1.000,0.997,0.986,1.000,1.000,1.000,1.000,1.000
```

Setting `data_min` to `0.0` will cause white base outlines to correspond with zero base-pair probability
and setting `data_max` to `1.0` will cause red base outlines to correspond with 100% base-pair probability.

(The `color_gradient_direction` URL parameter is also set to `reverse`.)

```
https://code.rnacanvas.app?sequence=AGAGUAGCAUUCUGCUUUAGACUGUUAACUUUAUGAACCACGCGUGUCACGUGGGGAGAGUUAACAGCGCCC&dot_bracket=(((((((....)))))))...(((((((((((.....(((((.......)))))..))))))))))).....&data=0.689,0.947,0.981,0.986,0.986,0.980,0.938,0.989,0.991,0.998,0.998,0.938,0.980,0.986,0.986,0.981,0.947,0.689,0.999,0.999,0.999,0.986,0.997,1.000,0.999,0.998,0.998,0.999,1.000,0.998,0.987,0.894,1.000,1.000,1.000,1.000,1.000,0.808,0.808,0.806,0.805,0.788,0.805,0.805,0.841,1.000,1.000,1.000,0.841,0.788,0.805,0.806,0.808,0.808,0.813,0.892,0.894,0.987,0.998,1.000,0.999,0.998,0.998,0.999,1.000,0.997,0.986,1.000,1.000,1.000,1.000,1.000&color_gradient_direction=reverse&data_min=0.0&data_max=1.0
```

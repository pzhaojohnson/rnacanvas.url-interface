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

### Hiding the peripheral UI

The peripheral UI (which includes things like the lower-left Toolbar and top-left `Open`, `Save` and `Export` buttons)
can be hidden by setting the `peripheral_ui` URL parameter to `none`.

```
https://code.rnacanvas.app?peripheral_ui=none&sequence=AAGGGGAAAACCCCAAGGGGAAAACCCCAA&dot_bracket=..((((....))))..((((....))))..
```

### Showing a minimal peripheral UI

Alternatively, a minimalistic peripheral UI can be shown.

At this time the minimal peripheral UI simply includes a top-right `Edit` button
to reopen the current drawing in a new tab
(with the full peripheral UI to be shown in the new tab).

```
https://code.rnacanvas.app?peripheral_ui=minimal&sequence=AAGGGGAAAACCCCAAGGGGAAAACCCCAA&dot_bracket=..((((....))))..((((....))))..
```

# Coloring bases according to data

Bases can be given colored outlines according to data
(e.g., base-pair probability data, positional entropy data)
using the `data` URL parameter.

For example, suppose the following structure...

```
AGAGUAGCAUUCUGCUUUAGACUGUUAACUUUAUGAACCACGCGUGUCACGUGGGGAGAGUUAACAGCGCCC
(((((((....)))))))...(((((((((((.....(((((.......)))))..))))))))))).....
```

...has the following positional entropy data.

```
0.911,0.323,0.159,0.120,0.116,0.161,0.378,0.090,0.077,0.017,0.024,0.351,0.170,0.121,0.115,0.158,0.316,0.929,0.007,0.007,0.007,0.110,0.026,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.109,0.507,-0.000,-0.000,0.000,0.000,0.000,0.911,0.924,0.710,0.762,0.838,0.711,0.712,0.632,0.001,0.000,-0.000,0.632,0.832,0.713,0.717,0.742,0.896,0.881,0.500,0.495,0.109,0.027,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.110,0.001,0.005,0.005,-0.000,-0.000
```

(Each comma-separated value is the positional entropy of a residue in the structure.)

The following URL draws the structure
and gives each base a colored outline according to its positional entropy value.

```
https://code.rnacanvas.app?sequence=AGAGUAGCAUUCUGCUUUAGACUGUUAACUUUAUGAACCACGCGUGUCACGUGGGGAGAGUUAACAGCGCCC&dot_bracket=(((((((....)))))))...(((((((((((.....(((((.......)))))..))))))))))).....&data=0.911,0.323,0.159,0.120,0.116,0.161,0.378,0.090,0.077,0.017,0.024,0.351,0.170,0.121,0.115,0.158,0.316,0.929,0.007,0.007,0.007,0.110,0.026,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.109,0.507,-0.000,-0.000,0.000,0.000,0.000,0.911,0.924,0.710,0.762,0.838,0.711,0.712,0.632,0.001,0.000,-0.000,0.632,0.832,0.713,0.717,0.742,0.896,0.881,0.500,0.495,0.109,0.027,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.110,0.001,0.005,0.005,-0.000,-0.000
```

### Changing the color gradient

By default base outlines are colored along a white-to-red gradient.

Base outlines can be colored along a gradient similar to what [RNAfold](http://rna.tbi.univie.ac.at/cgi-bin/RNAWebSuite/RNAfold.cgi) uses
by setting the `color_gradient` URL parameter to `RNAfold`.

```
https://code.rnacanvas.app?sequence=AGAGUAGCAUUCUGCUUUAGACUGUUAACUUUAUGAACCACGCGUGUCACGUGGGGAGAGUUAACAGCGCCC&dot_bracket=(((((((....)))))))...(((((((((((.....(((((.......)))))..))))))))))).....&data=0.911,0.323,0.159,0.120,0.116,0.161,0.378,0.090,0.077,0.017,0.024,0.351,0.170,0.121,0.115,0.158,0.316,0.929,0.007,0.007,0.007,0.110,0.026,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.109,0.507,-0.000,-0.000,0.000,0.000,0.000,0.911,0.924,0.710,0.762,0.838,0.711,0.712,0.632,0.001,0.000,-0.000,0.632,0.832,0.713,0.717,0.742,0.896,0.881,0.500,0.495,0.109,0.027,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.110,0.001,0.005,0.005,-0.000,-0.000&color_gradient=RNAfold
```

### Reversing the color gradient

By default lower values correspond to the "beginning" of the color gradient
and higher values correspond to the "end" of the color gradient.

Setting the `color_gradient_direction` URL paramter to `reverse` will reverse this.

```
https://code.rnacanvas.app?sequence=AGAGUAGCAUUCUGCUUUAGACUGUUAACUUUAUGAACCACGCGUGUCACGUGGGGAGAGUUAACAGCGCCC&dot_bracket=(((((((....)))))))...(((((((((((.....(((((.......)))))..))))))))))).....&data=0.911,0.323,0.159,0.120,0.116,0.161,0.378,0.090,0.077,0.017,0.024,0.351,0.170,0.121,0.115,0.158,0.316,0.929,0.007,0.007,0.007,0.110,0.026,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.109,0.507,-0.000,-0.000,0.000,0.000,0.000,0.911,0.924,0.710,0.762,0.838,0.711,0.712,0.632,0.001,0.000,-0.000,0.632,0.832,0.713,0.717,0.742,0.896,0.881,0.500,0.495,0.109,0.027,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.110,0.001,0.005,0.005,-0.000,-0.000&color_gradient=RNAfold&color_gradient_direction=reverse
```

Reversing the direction of a color gradient can be useful
when one's data are base-pair probability data
rather than positional entropy data.

### Setting color gradient boundaries

By default the minimum data value will be made to correspond to the very beginning of the color gradient
and the maximum data value will be made to correspond to the very end of the color gradient.

Explicitly setting the `data_min` and `data_max` URL parameters allows one to control where data values fall along the color gradient.

For example, suppose the structure...

```
GGCAGUCGCAUACGAUAUUACGUGC
((..((((....)))).))......
```

...has the following base-pair probability data.

```
0.121,0.070,0.502,0.828,0.428,0.450,0.457,0.434,0.579,0.929,0.645,0.581,0.434,0.457,0.450,0.428,0.995,0.197,0.071,0.159,0.549,0.498,0.340,0.419,0.732
```

Setting `data_min` to `0.0` will cause bases with zero base-pair probability to have white outlines
and setting `data_max` to `1.0` will cause bases with 100% base-pair probability to have red outlines.

```
https://code.rnacanvas.app?sequence=GGCAGUCGCAUACGAUAUUACGUGC&dot_bracket=((..((((....)))).))......&data=0.121,0.070,0.502,0.828,0.428,0.450,0.457,0.434,0.579,0.929,0.645,0.581,0.434,0.457,0.450,0.428,0.995,0.197,0.071,0.159,0.549,0.498,0.340,0.419,0.732
&data_min=0.0&data_max=1.0
```

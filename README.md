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

### Color bases according to data

Bases can be given colored outlines according to data
(e.g., base-pair probability data, positional entropy data)
by utilizing the `data` URL parameter.

For example, the following structure...

```
AGAGUAGCAUUCUGCUUUAGACUGUUAACUUUAUGAACCACGCGUGUCACGUGGGGAGAGUUAACAGCGCCC
(((((((....)))))))...(((((((((((.....(((((.......)))))..))))))))))).....
```

...has the following positional entropy data.

Each value indicates the positional entropy of a single residue in the structure
(with values separated by commas).

```
0.911,0.323,0.159,0.120,0.116,0.161,0.378,0.090,0.077,0.017,0.024,0.351,0.170,0.121,0.115,0.158,0.316,0.929,0.007,0.007,0.007,0.110,0.026,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.109,0.507,-0.000,-0.000,0.000,0.000,0.000,0.911,0.924,0.710,0.762,0.838,0.711,0.712,0.632,0.001,0.000,-0.000,0.632,0.832,0.713,0.717,0.742,0.896,0.881,0.500,0.495,0.109,0.027,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.110,0.001,0.005,0.005,-0.000,-0.000
```

This structure is drawn by the following URL
(giving bases colored outlines according to their positional entropy).

```
https://code.rnacanvas.app?sequence=AGAGUAGCAUUCUGCUUUAGACUGUUAACUUUAUGAACCACGCGUGUCACGUGGGGAGAGUUAACAGCGCCC&dot_bracket=(((((((....)))))))...(((((((((((.....(((((.......)))))..))))))))))).....&data=0.911,0.323,0.159,0.120,0.116,0.161,0.378,0.090,0.077,0.017,0.024,0.351,0.170,0.121,0.115,0.158,0.316,0.929,0.007,0.007,0.007,0.110,0.026,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.109,0.507,-0.000,-0.000,0.000,0.000,0.000,0.911,0.924,0.710,0.762,0.838,0.711,0.712,0.632,0.001,0.000,-0.000,0.632,0.832,0.713,0.717,0.742,0.896,0.881,0.500,0.495,0.109,0.027,0.001,0.011,0.017,0.017,0.011,0.001,0.026,0.110,0.001,0.005,0.005,-0.000,-0.000
```

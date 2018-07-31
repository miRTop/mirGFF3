A proxy for [miRNA](https://en.wikipedia.org/wiki/MicroRNA)/[isomiR](https://en.wikipedia.org/wiki/IsomiR) data analysis where all tools meet with the idea to create an ecosystem of data analysis promoting community collaboration.

[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](http://www.repostatus.org/badges/latest/active.svg)](http://www.repostatus.org/#active)
[![Description](https://img.shields.io/badge/gff3-definition-yellow.svg)](https://github.com/miRTop/mirGFF3/blob/master/definition.md)
[![Example](https://img.shields.io/badge/gff3-example-green.svg)](https://github.com/miRTop/mirGFF3/blob/master/example.gff)
[![Example](https://img.shields.io/badge/FAIRsharing-accepted-blue.svg)](https://fairsharing.org/bsg-s001218)
[![Example](https://img.shields.io/badge/EDMA-accepted-blue.svg)](http://bioportal.bioontology.org/ontologies/EDAM?p=classes&conceptid=format_3864)



**Introduction**

As discussed here: https://github.com/miRTop/incubator/issues/10 we've defined a GFF3 format for output of small RNA pipelines focused on miRNA data currently. We is an open community project ([read more](http://mirtop.github.io)) and joint us!

This output is based on the current GFF3 definition: https://github.com/The-Sequence-Ontology/Specifications/blob/master/gff3.md

Note: Keep in mind this is for the output of a pipeline, so we know there will be bias toward methodology, but the idea is to put enough information to be able to re-analyze or filter sequences using information described here. As well, it would be a proxy for downstream analysis or packages.

**Advantages**

* Developers of miRNA detection and annotation tools can open their results to other tools and communities using this format.

* Developers of downstream analysis can use the output from any supported annotation tool to work on variant calling, visualization, filtering, ensemble strategy to call isomiRs, etc ...

> If you want to fo fast, go alone;
> If you want to go far, go together

*by Tracy Teal (Data Carpenter CEO, GCC BOSC 2018)* [see slides](https://gccbosc2018.sched.com/event/EQF7/opening-keynote-tracy-k-teal)

**Version**

VERSION: 0.9

**Contact**

[miRTop group](https://mirTop.github.io)

Authors: @lpantano @gurgese @ThomasDesvignes @mhalushka @mlhack @keilbeck @BastianFromm @ivlachos @TJU-CMC @sbb25

Share any [questions and/or suggestions](https://github.com/miRTop/mirGFF3/issues/new)

**Compatible tools**

* miRGe2.0
* bcbio - seqbuster(miraligner)
* sRNAbench
* isomiR-SEA
* PROST!
* isomiRs

Make your tool [compatible](https://github.com/miRTop/mirtop/issues/new), open an issue today!

**API**

* Convert to GFF
* Convert from GFF
* Validator

Link to the API: https://mirtop.readthedocs.io/en/latest/

**Implementation**

* Submitted to EDAM Ontology
* FAIRsharing: https://fairsharing.org/bsg-s001218


**Presentations**

* [GCCBOSC2018](https://f1000research.com/slides/7-953)<sup>1</sup>

*Note: if you presented this work, please chime in this issue* # TODO missing link


**Reference**

1: Desvignes T, EIlbeck K, S. Vlachos I et al. miRTOP: An open source community project for the development of a unified format file for miRNA data [version 1; not peer reviewed]. F1000Research 2018, 7(ISCB Comm J):953 (slides) (doi: 10.7490/f1000research.1115724.1)

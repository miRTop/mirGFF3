A proxy for miRNA/isomiR(need REF) data analysis where all tools meet with the idea to create an ecosystem of data analysis promoting community collaboration.

[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](http://www.repostatus.org/badges/latest/active.svg)](http://www.repostatus.org/#active)
[![Description](https://img.shields.io/badge/gff3-definition-yellow.svg)](https://github.com/miRTop/mirGFF3/blob/master/definition.md)
[![Example](https://img.shields.io/badge/gff3-example-green.svg)](https://github.com/miRTop/mirGFF3/blob/master/example.md)

**Introduction**

As discussed here: https://github.com/miRTop/incubator/issues/10 we've defined a GFF3 format for output of small RNA pipelines focused on miRNA data currently.

This output is based on the current GFF3 definition: https://github.com/The-Sequence-Ontology/Specifications/blob/master/gff3.md

Note: Keep in mind this is for the output of a pipeline, so we know there will be bias toward methodology, but the idea is to put enough information to be able to re-analyze or filter sequences using information described here. As well, it would be a proxy for downstream analysis or packages.

**Advantages**

* Developers of miRNA detection and annotation tools can open their results to other tools and communities using this format.

* Developers of downstream analysis can use the output from any supported annotation tool to work on variant calling, visualization, filtering, ensemble strategy to call isomiRs, etc ...

> If you want to fo fast, go alone;
> If you want to go far, go together

*by Tracy Teal (Data Carpenter CEO, GCC BOSC 2018)* # TODO need reference

**Version**

VERSION: 1.0

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
* Submitted to FAREsharing.org


**Presentations**

* GCCBOST2018 # TODO missing link

*Note: if you presented this work, please chime in this issue* # TODO missing link

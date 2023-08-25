---
title: Data reception
description: Introduction to data reception
---

Uniform processes (such as quality control and standardisation) to receive (download) or access (API) both data and metadata in a consistent way enabling infrastructure to adhere to global standards and principles (e.g. GA4GH, FAIR) for genotypic and phenotypic data. Data reception means logically describing datasets to an extent that they can become actionable on the 1+MG infrastructure even if they are stored nationally or locally.

Physical transfer of data into the 1+MG Data Node (when required) incl., legal transfer of data to enable visibility in a data catalogue. While 1+MG could be able to provide access to current genomic data collections across Europe the 1+MG Framework define the quality requirements for a data collection to be 1+MG compliant (e.g. re-consent and data management activities could be required for a existing dat collection to be 1+MG compliant)  

###  Synthetic Data Catalogue <span class="badge badge-dark">Recommended<i class="fa-solid fa-thumbs-up"></i></span>
The Synthetic Data Catalogue will be available through the GDI User Portal with clear labelling to enable semi automated discovery, filtering, and access.

### [Htsget](https://www.ga4gh.org/product/htsget/) <span class="badge badge-dark">Recommended<i class="fa-solid fa-thumbs-up"></i></span>
htsget is a data streaming protocol that allows genetic data to be securely streamed from one location to another. It supports range-based queries,for example a user can request a single region, exon or gene to be streamed to a location. htsget is a secure protocol, with alldata transmission running over https. The use of htsget can be used to restrict access to genomic regions, preventing users streaming data from certain genes for example.

### [Data Repository Service (DRS)](https://ga4gh.github.io/data-repository-service-schemas/preview/release/drs-1.2.0/docs/) <span class="badge badge-dark">Recommended<i class="fa-solid fa-thumbs-up"></i></span>
DRS is a GA4GH standard API that provides a generic interface to data repositories so data consumers, including workflow systems, can access data objects in a single, standard way regardless of where they are stored and how they are managed. The primary functionality of DRS is to map a logical ID to a means for physically retrieving the data represented by the ID. 

### [Refget](https://www.ga4gh.org/product/refget/) <span class="badge badge-warning">Required<i class="fa-sharp fa-regular fa-star"></i></span>
The first step of any genomic analysis is mapping the new sequence data to a reference sequence — a list of three billion base pairs that have been generally accepted as “normal” for a given population or subgroup. However, standard conventions for naming and identifying reference sequences are lacking. Different organisations refer to the same sequence differently. Developed by the GA4GH, the refget API provides a framework to retrieve reference sequences by using an algorithm to derive a unique identifier. The identifier can then be used to verify the integrity of the reference sequence.




**We are still working on the content for this page.** If you are interested in adding to the page, then:

[Feel free to contribute](how_to_contribute){: class="btn btn-primary btn-lg rounded-pill"}

This is a community-driven website, so contributions are welcome! You will, of course, be listed as a contributor on the page.



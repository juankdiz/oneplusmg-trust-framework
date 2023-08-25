---
title: Storage and Interfaces
description: Introduction to Storage and Interfaces
---

Organisations store data and offer interfaces (APIs) following international standards that form the technically interoperable infrastructure backbone. Service building is assumed to leverage national and European investments in e-infrastructure capacities. Storage & interfaces need to provide techniques ensuring data privacy and confidentiality.

### [Federated European Genome Archive (EGA)](https://ega-archive.org/federated) Technologies <span class="badge badge-dark">Recommended<i class="fa-solid fa-thumbs-up"></i></span>
FEGA-based Technologies are used for the establishment of the 1+MG National Nodes that will store the genomic, phenotypic and the corresponding metada.

### [Phenopackets](https://www.ga4gh.org/product/phenopackets/) <span class="badge badge-warning">Required<i class="fa-sharp fa-regular fa-star"></i></span>
The Phenopacket standard is designed to allow phenotypic information to be exchanged in a consistent standardised and structured format. Itlinks phenotypic information with individual,genetic, and disease information. Phenopackets are already used by the rare disease community, for example in the Solve-RD project and RD-Connect, which makes them ideal as a standard to drive the exchange of phenotypic information between nodes or services.
### [VCF](https://www.ga4gh.org/product/genetic-variation-formats-vcf/) <span class="badge badge-warning">Required<i class="fa-sharp fa-regular fa-star"></i></span>, [SAM/BAM](https://www.ga4gh.org/product/sam-bam/) <span class="badge badge-dark">Recommended<i class="fa-solid fa-thumbs-up"></i></span> /[CRAM](https://www.ga4gh.org/product/cram/) <span class="badge badge-warning">Required<i class="fa-sharp fa-regular fa-star"></i></span>
The VCF and SAM / BAM / CRAM file formats are used to store genetic data in a standard format. SAM / BAM / CRAM files store the complete genetic data for a genomic region, including the depth of coverage for aligned data across these regions, and the quality of the sequenced reads. BAM is a binary version of a SAM file, while CRAM is a newer file format that compresses the data to a greater extent than SAM or BAM, reducing the amount of storage required for a set amount of genomic data.VCF files store the variation data detected in one or more individuals, ensuring that the file sizes are reduced, but detailing the specific alleles that are different from the reference sequence.All file types can be indexed creating a separate index file, which is a requirement for distributing the files by htsget.

### [Crypt4GH](https://www.ga4gh.org/product/genetic-data-encryption-crypt4gh/) <span class="badge badge-dark">Recommended<i class="fa-solid fa-thumbs-up"></i></span>
Crypt4GH is an encryption standard that uses one or more encryption keys to encrypt one or more regions of a file, such as a VCF or SAM /BAM / CRAM file, but can be used for any file type or format. The encryption key or keys that are used to encrypt the file itself are added to the header of the file encrypted with secondary keys. To allow the decryption of one or more regions of the file, the user just needs the specific key or keys to decrypt the portion of the header which encrypted the region of interest in the file, and then use that key to decrypt the required region. This has the advantage that encrypting the file for different users just needs the specific keys to be encrypted per user, reducing re-encryption overhead. It also allows only specific regions of a file to be decrypted for certain users, restricting access to certain regions or genes.

### [Simpl](https://digital-strategy.ec.europa.eu/en/news/simpl-cloud-edge-federations-and-data-spaces-made-simple-updated-august-2023) <span class="badge badge-warning">Required<i class="fa-sharp fa-regular fa-star"></i></span>
Simpl is the smart middleware that will enable cloud-to-edge federations and support all major data initiatives funded by the European Commission, such as common European data spaces. It will be the basis for a European Cloud Federation enabling the operation and interconnection within and in between various European data spaces and the safe migration of the users to the cloud.






**We are still working on the content for this page.** If you are interested in adding to the page, then:

[Feel free to contribute](how_to_contribute){: class="btn btn-primary btn-lg rounded-pill"}

This is a community-driven website, so contributions are welcome! You will, of course, be listed as a contributor on the page.



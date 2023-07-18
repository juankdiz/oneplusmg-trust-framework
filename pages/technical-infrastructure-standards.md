---
title: 'Technical Infrastructure: standards, proofs of concept, and APIs'
description: Introduction to Technical Infrastructure standards
---

B1MG defined the architecture, shared interfaces, and possible virtualisation platforms required to achieve technical interoperability. In addition, the proposed infrastructure must support semantic interoperability, so a variety of international standards were proposed to support this.


<img src="{{ 'assets/img/standard-interoperability.jpg' | relative_url }}" class="m-2" style="max-width: 100%; max-height: 100%; vertical-align: middle" alt="B1MG objectives for interoperability EOSC model" />

Global Alliance for Genomics and Health (GA4GH) standards are used to link the different applications supporting the B1MG five technical functionalities within the Proof of Concept.  The chosen standards aligned with the functionalities can be seen in the diagram below.  While none of these standards are required for a Node to implement, they can be seen as the interoperability backbone of the infrastructure.

<img src="{{ 'assets/img/data-infrastructure.png' | relative_url }}" class="m-2" style="max-width: 100%; max-height: 100%; vertical-align: middle" alt="Standard Infrastructure" />

## Data Discovery
### [Beacon](https://www.ga4gh.org/product/beacon-api/)
The GA4GH Beacon V2 standard is a data discoverability standard that underpins the Beacon service described above. Beacon V2 allows gene or region level queries, and phenotype queries. Within the rare disease use case this allows researchers to query for nodes containing individuals who share variants in the same region or gene, share similar phenotypes or disease, or datasets that correspond to certain data use conditions.  The user would then be able to request full access to the underlying data.

## Access Management
### [Data Use Ontology](https://www.ga4gh.org/product/data-use-ontology-duo/)
The Data Use Ontology (DUO) is an ontology that describes the data use conditions that are applied to one or more datasets held within a node. As the DUO is an ontology, it is bydesign machine-readable. The conditions can affect the type of secondary use that can be performed on the original data. For example, the data can be restricted to a certain location,or to research within a certain disease. Each release of the DUO is versioned, ensuring that historic DUO attributes are maintained when the definition of the term is modified to reflect changes in the legal and technological landscape around genomic data.The DUO can be seen as part of the data Discoverability Functionality, and the Data Access Management Tools functionality. This is because the machine readable attribute of the DUOallows prospective users to query data sets based on the data use conditions - for example user A may wish to research disease X, so can filter out from available datasets all but that disease. The DUO can also be used to determine dataaccess, for example by determining if the researcher who is applying for data access intends to use the data for a purpose allowed by the Data Access Committee or data controller.

### [Authentication and Authorization Infrastructure](https://www.ga4gh.org/product/aai/) and [Passports](https://www.ga4gh.org/product/ga4gh-passports/)
The required Authentication and Authorisation Infrastructure (AAI) and Passport standards are defined by the GA4GH. These standards specify the way a user’s identity and access permissions can be distributed and understood across a federated network. The standards also allow a user to link multiple identities together.For example, the ELIXIR AAIconforms12to the GA4GH AAI standard, and supports the GA4GH passport standard. This allows users who have an ELIXIR identity to link other identities to their ELIXIR identity. This allows individual nodes to maintain their own identity provider,if required, but still allow a user to use their ELIXIR identity to access authorised resources across a federated network. For example, a user can link their ELIXIR identity to an EGA identity, which would allow the user to access the Resource Entitlement Management System (REMS) hosted by CSC to administer user permissions using their ELIXIR identity, and then access the EGA using the same identity while internally the EGA identifies the user using the EGA account. The granularity of data access can be defined by the DAC depending on the ELSI requirements,for example data access can be granted to specific files, files associated with an individual, or to a cohort.


## Data Processing
### [Workflow](https://www.ga4gh.org/product/workflow-execution-service-wes/) & [Task Execution Service](https://www.ga4gh.org/product/task-execution-service-tes/)
The GA4GH Workflow Execution Service (WES) standard specifies how complex analytic pipelines can be specified in a standardised way to allow these pipelines to run in different locations, for example at different federated node:an important requirement in allowing users to send the analysis to the data rather than bring the data to the analysis which helps to ensure the data remains secure and conforms to the ELSI issues that apply to it. The Task Execution Service (TES) allows analysis pipelines to run on a wide range of heterogeneous infrastructure. For example, a user may wish to run the same variant calling pipeline on data hosted at three different nodes,but the compute infrastructure used by these nodes is different. While WES allows the pipeline to be specified in a standardised way, TES ensures that the task required to run the pipeline can be executed on different types of compute infrastructure, such as different high performance computing (HPC) orCloud environments. WES and TES together ensure that identical, repeatable, and consistent analysis can be run on different federated nodes irrespective of the underlying compute infrastructure.


## Data Reception
### [Htsget](https://www.ga4gh.org/product/htsget/)
Htsget is a data streaming protocol that allows genetic data to be securely streamed from one location to another. It supports range-based queries,for example a user can request a single region, exon or gene to be streamed to a location. htsget is a secure protocol, with alldata transmission running over https. The use of htsget can be used to restrict access to genomic regions, preventing users streaming data from certain genes for example.


## Storage and Interfaces
### [Phenopackets](https://www.ga4gh.org/product/phenopackets/)
The Phenopacket standard is designed to allow phenotypic information to be exchanged in a consistent standardised and structured format. Itlinks phenotypic information with individual,genetic, and disease information. Phenopackets are already used by the rare disease community, for example in the Solve-RD project and RD-Connect, which makes them ideal as a standard to drive the exchange of phenotypic information between nodes or services.

### [VCF](https://www.ga4gh.org/product/genetic-variation-formats-vcf/), [SAM/BAM](https://www.ga4gh.org/product/sam-bam/)/[CRAM](https://www.ga4gh.org/product/cram/)
The VCF and SAM / BAM / CRAM file formats are used to store genetic data in a standard format. SAM / BAM / CRAM files store the complete genetic data for a genomic region, including the depth of coverage for aligned data across these regions, and the quality of the sequenced reads. BAM is a binary version of a SAM file, while CRAM is a newer file format that compresses the data to a greater extent than SAM or BAM, reducing the amount of storage required for a set amount of genomic data.VCF files store the variation data detected in one or more individuals, ensuring that the file sizes are reduced, but detailing the specific alleles that are different from the reference sequence.All file types can be indexed creating a separate index file, which is a requirement for distributing the files by htsget.

### [Crypt4GH](https://www.ga4gh.org/product/genetic-data-encryption-crypt4gh/)
Crypt4GH is an encryption standard that uses one or more encryption keys to encrypt one or more regions of a file, such as a VCF or SAM /BAM / CRAM files, but can be used for any file type of format. The encryption key or keys that are used to encrypt the file itself are added to the header of the file encrypted with secondary keys. To allow decryption of one or more regions of the file, the user just needs the specific key or keys to decrypt the portion of the header which encrypted the region of interest in the file, and then use that key to decrypt the required region. This has the advantage that encrypting the file for different users just needs the specific keys to be encrypted per user,reducing re-encryption overhead. It also allows only specific regions of a file to be decrypted for certain users, restricting access to certain regions or genes.

### [Documented best practices in sharing and linking phenotypic and genetic data](https://zenodo.org/record/7342855)
This is the second version of documented best practices in sharing and linking phenotypic and genetic data. It identifies and describes best practices on sharing and linking phenotypic and genetic data in both the healthcare sector as in the research setting to, as much as possible, avoid reinventing the wheel, learn from previous/current existing projects to improve performance and avoid mistakes made by others. The listed ’best practices’ have been identified by the 1+MG WG3 experts, who are nominated by the Member States, and are exemplary practices that have achieved results which could be used for larger-scale cross-border initiatives.

The areas of best practices covered are “data models and templates”, “Data interoperability, ontology and controlled terminology, ontology collections, mappings”, “Data standards”, “Data exchange standards”, “Data infrastructure, data management platforms and tools”, “Data governance, genomics data framework”, and “Data dictionaries”.

### [Phenotypic and clinical metadata framework 1v0](https://zenodo.org/record/6573854)
The aim of the 1+MG member states initiative with coordination support of the Beyond 1 Million Genomes (B1MG) consortium is to develop a pan-European genome-based health data infrastructure to further develop and operationalise personalised medicine and to understand pharmacogenomics. In order to support the 1+MG member states initiative ambitions for sustainability policies regarding assets in the field of personalised medicine interoperability, a set of simple but well-aligned instruments needs to be prepared. One of the crucial instruments for1+MG is a phenotypic and clinical metadata framework which describes, in a commonly understandable language, the principles, models and recommendations for sharing and linking of phenotypic and clinical metadata and genetic metadata between the member states.

The current framework document proposes to adhere to standards for data capture and exchange. The main target is to provide guidance on which standards, terminologies and tools to use. Best practices, describing which ontologies are currently implemented in each member state, are described elsewhere (Deliverable 3.8:Documents Best practices in sharing and linking phenotypic and genetic data - live working document).

This framework document will be part of the entire B1MG framework where other crucial instruments are taken care of by other work packages/working groups like Governance, ELSI and Technical Infrastructure. The B1MG framework document first of all aims at the 1+MG initiative while at the same time could be used as a base for the European Health Data Space(EHDS)2 and/or genomic data space.

### [Phenotypic and clinical metadata framework 2v0](https://zenodo.org/record/7554481)
One of the crucial instruments for 1+MG is a phenotypic and clinical metadata framework which describes, in a commonly understandable language, the principles, models, and recommendations for sharing and linking of phenotypic and clinical metadata and genetic metadata between the member states.  This framework document proposes to adhere to standards for data capture and exchange.  It provides guidance on which standards, terminologies, and tools to use.  

**We are still working on the content for this page.** If you are interested in adding to the page, then:

[Feel free to contribute](how_to_contribute){: class="btn btn-primary btn-lg rounded-pill"}

This is a community-driven website, so contributions are welcome! You will, of course, be listed as a contributor on the page.




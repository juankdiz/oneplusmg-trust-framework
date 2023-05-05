---
title: Technical Infrastructure standards
description: Introduction to Technical Infrastructure standards
---

B1MG defined the architecture, shared interfaces, and possible virtualisation platforms required to achieve technical interoperability. In addition, the proposed infrastructure must support semantic interoperability, so a variety of international standards were proposed to support this.


<img src="{{ 'assets/img/standard-interoperability.jpg' | relative_url }}" class="m-2" style="max-width: 100%; max-height: 100%; vertical-align: middle" alt="B1MG objectives for interoperability EOSC model" />

Global Alliance for Genomics and Health (GA4GH) standards are used to link the different applications supporting the B1MG five technical functionalities within the Proof of Concept.  The chosen standards aligned with the functionalities can be seen in the diagram below.  While none of these standards are required for a Node to implement, they can be seen as the interoperability backbone of the infrastructure.

<img src="{{ 'assets/img/GA4GH-GIF.jpg' | relative_url }}" class="m-2" style="max-width: 100%; max-height: 100%; vertical-align: middle" alt="GA4GH Beacon V2 standard" />

## Beacon
The GA4GH Beacon V2 standard is a data discoverability standard that underpins the Beacon service described above. Beacon V2 allows gene or region level queries, and phenotype queries. Within the rare disease use case this allows researchers to query for nodes containing individuals who share variants in the same region or gene, share similar phenotypes or disease, or datasets that correspond to certain data use conditions.  The user would then be able to request full access to the underlying data.

## Data Use Ontology
The Data Use Ontology (DUO) is an ontology that describes the data use conditions that are applied to one or more datasets held within a node. As the DUO is an ontology, it is bydesign machine-readable. The conditions can affect the type of secondary use that can be performed on the original data. For example, the data can be restricted to a certain location,or to research within a certain disease. Each release of the DUO is versioned, ensuring that historic DUO attributes are maintained when the definition of the term is modified to reflect changes in the legal and technological landscape around genomic data.The DUO can be seen as part of the data Discoverability Functionality, and the Data Access Management Tools functionality. This is because the machine readable attribute of the DUOallows prospective users to query data sets based on the data use conditions - for example user A may wish to research disease X, so can filter out from available datasets all but that disease. The DUO can also be used to determine dataaccess, for example by determining if the researcher who is applying for data access intends to use the data for a purpose allowed by the Data Access Committee or data controller.

## htsget
htsget is a data streaming protocol that allows genetic data to be securely streamed from one location to another. It supports range-based queries,for example a user can request a single region, exon or gene to be streamed to a location. htsget is a secure protocol, with alldata transmission running over https. The use of htsget can be used to restrict access to genomic regions, preventing users streaming data from certain genes for example.

## Phenopackets
The Phenopacket standard is designed to allow phenotypic information to be exchanged in a consistent standardised and structured format. Itlinks phenotypic information with individual,genetic, and disease information. Phenopackets are already used by the rare disease community, for example in the Solve-RD project and RD-Connect, which makes them ideal as a standard to drive the exchange of phenotypic information between nodes or services.

## VCF, SAM/BAM/CRAM
The VCF and SAM / BAM / CRAM file formats are used to store genetic data in a standard format. SAM / BAM / CRAM files store the complete genetic data for a genomic region, including the depth of coverage for aligned data across these regions, and the quality of the sequenced reads. BAM is a binary version of a SAM file, while CRAM is a newer file format that compresses the data to a greater extent than SAM or BAM, reducing the amount of storage required for a set amount of genomic data.VCF files store the variation data detected in one or more individuals, ensuring that the file sizes are reduced, but detailing the specific alleles that are different from the reference sequence.All file types can be indexed creating a separate index file, which is a requirement for distributing the files by htsget.

## Crypt4GH
Crypt4GH is an encryption standard that uses one or more encryption keys to encrypt one or more regions of a file, such as a VCF or SAM /BAM / CRAM files, but can be used for any file type of format. The encryption key or keys that are used to encrypt the file itself are added to the header of the file encrypted with secondary keys. To allow decryption of one or more regions of the file, the user just needs the specific key or keys to decrypt the portion of the header which encrypted the region of interest in the file, and then use that key to decrypt the required region. This has the advantage that encrypting the file for different users just needs the specific keys to be encrypted per user,reducing re-encryption overhead. It also allows only specific regions of a file to be decrypted for certain users, restricting access to certain regions or genes.

## Authentication and Authorization Infrastructure and Passports
The required Authentication and Authorisation Infrastructure (AAI) and Passport standards are defined by the GA4GH. These standards specify the way a user’s identity and access permissions can be distributed and understood across a federated network. The standards also allow a user to link multiple identities together.For example, the ELIXIR AAIconforms12to the GA4GH AAI standard, and supports the GA4GH passport standard. This allows users who have an ELIXIR identity to link other identities to their ELIXIR identity. This allows individual nodes to maintain their own identity provider,if required, but still allow a user to use their ELIXIR identity to access authorised resources across a federated network. For example, a user can link their ELIXIR identity to an EGA identity, which would allow the user to access the Resource Entitlement Management System (REMS) hosted by CSC to administer user permissions using their ELIXIR identity, and then access the EGA using the same identity while internally the EGA identifies the user using the EGA account. The granularity of data access can be defined by the DAC depending on the ELSI requirements,for example data access can be granted to specific files, files associated with an individual, or to a cohort.

## Workflow & Task Execution Service
The GA4GH Workflow Execution Service (WES) standard specifies how complex analytic pipelines can be specified in a standardised way to allow these pipelines to run in different locations, for example at different federated node:an important requirement in allowing users to send the analysis to the data rather than bring the data to the analysis which helps to ensure the data remains secure and conforms to the ELSI issues that apply to it. The Task Execution Service (TES) allows analysis pipelines to run on a wide range of heterogeneous infrastructure. For example, a user may wish to run the same variant calling pipeline on data hosted at three different nodes,but the compute infrastructure used by these nodes is different. While WES allows the pipeline to be specified in a standardised way, TES ensures that the task required to run the pipeline can be executed on different types of compute infrastructure, such as different high performance computing (HPC) orCloud environments. WES and TES together ensure that identical, repeatable, and consistent analysis can be run on different federated nodes irrespective of the underlying compute infrastructure.





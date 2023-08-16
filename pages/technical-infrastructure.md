---
title: 'Technical Infrastructure'
description: Introduction to Technical Infrastructure
---

The 1+MG technical infrastructure is broken down into five functionalities as defined in the 2021 paper titled, [“Towards a Proof of Concept of Federated Infrastructure for the EU 1+ Million Genome Initiative”](https://zenodo.org/record/6089583).  This includes: Data Discovery, Data Reception, Storage and Interfaces, Data Access Management, and Processing.  Each of these functionalities were originally defined as follows:

## Data Discoverability
Data discoverability Provides the public visibility to the combined 1+MG dataset by making selected descriptive metadata searchable. Data discovery service will collect summary level (but not sensitive) descriptions of all data available from the signatory states. It will link directly to Data Access Management where users can apply for data access.

## Data Reception
Uniform processes (such as quality control and standardisation) to receive (download) or access (API) both data and metadata in a consistent way enabling infrastructure to adhere to global standards and principles (e.g. GA4GH, FAIR) for genotypic and phenotypic data. Data reception means logically describing datasets to an extent that they can become actionable on the 1+MG infrastructure even if they are stored nationally or locally. 

## Storage & Interfaces
Organisations store data and offer interfaces (APIs) following international standards that form the technically interoperable infrastructure backbone. Service building is assumed to leverage national and European investments in e-infrastructure capacities. Storage & interfaces need to provide techniques ensuring data privacy and confidentiality.

## Data Access Management Tools
Sensitive data needs specialised services to manage data in an ELSI-compliant way. These include e.g. central access portal, central access review process, single collaboration/data use agreement. These tools store user applications for data use and the decisions from the data controllers, i.e. data access authorisations within the legal framework, as well as APIs and standards to communicate access rights to downstream infrastructure services. Together, these tools and processes facilitate and audit secure access for users on a chosen Data Processing service platform.

## Processing
Local, high-performance and cloud computing must fulfil appropriate security standards to provide processing capacities for human data coordinated in 1+MG. Distinct processing events happen on the infrastructure: Localisation of the data and code to the appropriate platform (local or distributed) and data analysis by the individual data user who has acquired the access rights for the intended data use. 


Global Alliance for Genomics and Health (GA4GH) standards are used to link the different applications supporting the five technical functionalities within the B1NG Proof of Concept.  The chosen standards aligned with the functionalities can be seen in the diagram below.  While none of these standards are required for a Node to implement, they can be seen as the interoperability backbone of the infrastructure.

<img src="{{ 'assets/img/data-infrastructure.png' | relative_url }}" class="m-2" style="max-width: 100%; max-height: 100%; vertical-align: middle" alt="Standard Infrastructure" />


**We are still working on the content for this page.** If you are interested in adding to the page, then:

[Feel free to contribute](how_to_contribute){: class="btn btn-primary btn-lg rounded-pill"}

This is a community-driven website, so contributions are welcome! You will, of course, be listed as a contributor on the page.




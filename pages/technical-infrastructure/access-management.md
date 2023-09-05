---
title: Access management
description: Introduction to access management
---

Sensitive data needs specialised services to manage data in an ELSI compliant way. These include e.g. central access portal, central access review process, single collaboration/data use agreement. These tools store user applications for data use and the decisions from the data controllers, i.e. data access authorisations within the legal framework, as well as APIs and standards to communicate access rights to downstream infrastructure services. Together, these tools and processes facilitate and audit secure access for users on a chosen Data Processing service platform.

### User Portal
Under development by the European Genomic Data Infrastructure project, the User Portal will be the main European-level entry point for data access within the infrastructure.


### [Data Use Ontology](https://www.ga4gh.org/product/data-use-ontology-duo/) <span class="badge badge-warning">Required<i class="fa-sharp fa-regular fa-star"></i></span>
The Data Use Ontology (DUO) is an ontology that describes the data use conditions that are applied to one or more datasets held within a node. As the DUO is an ontology, it is by design machine-readable. The conditions can affect the type of secondary use that can be performed on the original data. For example, the data can be restricted to a certain location, or to research within a certain disease. Each release of the DUO is versioned, ensuring that historic DUO attributes are maintained when the definition of the term is modified to reflect changes in the legal and technological landscape around genomic data.The DUO can be seen as part of the data Discoverability Functionality, and the Data Access Management Tools functionality. This is because the machine-readable attribute of the DUO allows prospective users to query data sets based on the data use conditions - for example, user A may wish to research disease X, so can filter out from available datasets all but that disease. The DUO can also be used to determine data access, for example by determining if the researcher who is applying for data access intends to use the data for a purpose allowed by the Data Access Committee or data controller.

### [Life Science Login](https://lifescience-ri.eu/ls-login/) <span class="badge badge-warning">Required<i class="fa-sharp fa-regular fa-star"></i></span>
The Life Science Login enables researchers to use their home organisation credentials or community or other identities (e.g. Google, Linkedin, LS ID) to sign in and access data and services they need. It also allows service providers (both in academia and industry) to control and manage access rights of their users and create different access levels for research groups or international projects.

### [REMS](https://www.elixir-finland.org/en/aai-rems-2/) <span class="badge badge-dark">Recommended<i class="fa-solid fa-thumbs-up"></i></span>
REMS (Resource Entitlement Management System), developed by CSC, is a tool that can be used to manage researchers’ access rights to bioinformatics databases. Through REMS, researchers can apply for access to research data, and the owners of the rights to the materials can process the received applications and manage access rights. Users log into REMS, for example, through the HAKA user identification system. After logging in, users can search for data resources.REMS transfers the application to the owner of the resource for approval and reports on the rights granted

### [Authentication and Authorization Infrastructure](https://www.ga4gh.org/product/aai/) <span class="badge badge-warning">Required<i class="fa-sharp fa-regular fa-star"></i></span> and [Passports](https://www.ga4gh.org/product/ga4gh-passports/) <span class="badge badge-warning">Required<i class="fa-sharp fa-regular fa-star"></i></span>
The required Authentication and Authorisation Infrastructure (AAI) and Passport standards are defined by the GA4GH. These standards specify the way a user’s identity and access permissions can be distributed and understood across a federated network. The standards also allow a user to link multiple identities together.For example, the ELIXIR AAI conforms to the GA4GH AAI standard, and supports the GA4GH passport standard. This allows users who have an ELIXIR identity to link other identities to their ELIXIR identity. This allows individual nodes to maintain their own identity provider, if required, but still allows a user to use their ELIXIR identity to access authorised resources across a federated network. For example, a user can link their ELIXIR identity to an EGA identity, which would allow the user to access the Resource Entitlement Management System (REMS) hosted by CSC to administer user permissions using their ELIXIR identity, and then access the EGA using the same identity while internally the EGA identifies the user using the EGA account. The granularity of data access can be defined by the DAC depending on the ELSI requirements, for example data access can be granted to specific files, files associated with an individual, or to a cohort.

### [eID](https://ec.europa.eu/digital-building-blocks/wikis/display/DIGITAL/eID) <span class="badge badge-warning">Required<i class="fa-sharp fa-regular fa-star"></i></span>
eID is a set of services provided by the European Commission to enable the mutual recognition of national electronic identification schemes (eID) across borders. It allows European citizens to use their national eIDs when accessing online services from other European countries.This is an EU Standard that the 1+MG data access management standards should be compatible with.

### [EU-Wallet](https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/european-digital-identity_en) <span class="badge badge-warning">Required<i class="fa-sharp fa-regular fa-star"></i></span>
The European Digital Identity will be available to EU citizens, residents, and businesses who want to identify themselves or provide confirmation of certain personal information. It can be used for both online and offline public and private services across the EU.  This is an EU Standard that the 1+MG data access management standards should be compatible with.




**We are still working on the content for this page.** If you are interested in adding to the page, then:

[Feel free to contribute](how_to_contribute){: class="btn btn-primary btn-lg rounded-pill"}

This is a community-driven website, so contributions are welcome! You will, of course, be listed as a contributor on the page.



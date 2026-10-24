
This guide is built on top of the FHIR standard and, where available, [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core/) and [AU Base](https://build.fhir.org/ig/hl7au/au-fhir-base/). 

The context of AU Encounter Record Summary within the set of HL7 AU standards is shown in the figure below:
- the **FHIR standard** is the foundation, which creates a common platform or foundation on which a variety of different solutions are implemented. References to the FHIR standard on this page include the HL7 International Core FHIR Specification, HL7 International Core Extensions FHIR Implementation Guide (Extensions Pack) and HL7 International HL7 Terminology (THO). 
- **AU Base** defines local concepts for use in an Australian context introducing relevant identifiers, terminology, extensions. 
- **AU Core** defines a set of conformance requirements that enforce a set of ‘minimum requirements’ on the local concepts from AU Base, specifying rules for the elements, extensions, vocabularies, and value sets, and the RESTful API interactions.
- **Use case IGs** (AU Patient Summary, AU eRequesting and AU Provider Directory) build on AU Core to address specific use cases, defining a set of conformance requirements on top of AU Core, using additional building blocks from AU Base as needed.

This layering of IGs balances relative adoption and implementation maturity of FHIR and requirements of the use cases involved.

  <div> 
    <img src="architecture.png" alt="Context of AU Encounter Record Summary within the set of HL7 AU standards" style="width:65%"/>
  </div>
*Figure 1: Context of AU Encounter Record Summary within the set of HL7 AU standards*
<br/>


### Relationship to AUCDI and Other IGs
The primary intent of the [AUCDI](https://sparked.csiro.au/index.php/sparked-products-resources/aucdi/) is to design and govern a collection of coherent, reusable building blocks known as data groups. These data groups specify “what” the clinical requirements of the clinical information that should be included for data entry, data use, and sharing of information supporting healthcare delivery. However, it does not specify 'how' the data is exchanged; this is the role fulfilled by the FHIR standard. AUCDI is not required to be implemented as a whole single product. Parts can be implemented as required for specific use cases. 

AUCDI R3 builds upon R1 and R2, expanding on the initial 'core', introducing additional data groups and data elements to support different use cases including those required for an encounter record summary. These AUCDI data groups comprising one or more data elements, references clinical terminology concepts, forming the foundation of a common language to allow systems to exchange semantically accurate data more efficiently for patient summaries.

AU Encounter Record Summary is a technical specification that addresses constraints and obligations on data representation for exchange. AU Encounter Record Summary enables system data to be mapped to an agreed FHIR format, produced, and consumed by systems in Australia.

AU Encounter Record Summary is based on, aligns to, and leverages international standards and other national standards. Corresponding profiles included in relevant FHIR implementation guides were reviewed and considered during the development process to ensure alignment and to facilitate adoption of this standard. These implementation guides include:
- [HL7 Cross Paradigm Implementation Guide: Gender Harmony - Sex and Gender Representation, Edition 1](https://hl7.org/xprod/ig/uv/gender-harmony/informative1/)
- [International Patient Access 1.1.0](https://hl7.org/fhir/uv/ipa/STU1.1/)
- [International Patient Summary 2.0.1](https://hl7.org/fhir/uv/ips/2.0.1/en/)
- [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core/)

The relationship of AU Encounter Record Summary to AUCDI and other implementation guides is shown in the figure below.

 <div> 
    <img src="context-colour.png" alt="Relationship to AUCDI and Other IGs" style="width:75%"/>
  </div>
*Figure 2: Relationship to AUCDI and Other IGs*
<br/>

Implementation Guide |Relationship
---|---
[AU Base](https://build.fhir.org/ig/hl7au/au-fhir-base/)|This IG defines Australian realm concepts including terminology, identifiers, and extensions. AU Encounter Record Summary uses AU Base, where available, as the basis for profiles that define the FHIR resources to be supported, and the elements, extensions, vocabularies, and value sets that SHALL be present are identified, and how they are used is defined. Where available and applicable, AU Base concepts are profiled in AU Core and inherited by AU Encounter Record Summary.
[HL7 Cross Paradigm Implementation Guide: Gender Harmony - Sex and Gender Representation](https://hl7.org/xprod/ig/uv/gender-harmony/informative1/)|This IG provides definitive guidance on how to exchange clinical sex and gender affirming information using HL7 models. Sex and gender concepts from this IG have been reviewed for the potential for adoption in Australia. Where adopted, these concepts are included by reference in AU Base, profiled in AU Core, and inherited by AU Encounter Record Summary.
[AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core/)|This IG defines a set of conformance requirements that enforce a set of 'minimum requirements' on the local concepts from AU Base, specifying the elements, extensions, vocabularies, and value sets that SHALL be present and how they SHALL be used. AU Core also defines a data access API, specifying the conformance requirements for RESTful interactions. AU Encounter Record Summary is compliant with the profile only requirements of AU Core, e.g. AU Core conformant data can be used to generate an AU Encounter Record Summary document and AU Encounter Record Summary conformant data can be accessed by an AU Core conformant requester.
[International Patient Access 1.1.0](https://hl7.org/fhir/uv/ipa/STU1.1/)|This IG describes how an application acting on behalf of a patient can access information about the patient from a clinical records system using a FHIR based API. The REST API and profiles in this IG were reviewed and considered during development of AU Core and AU Encounter Record Summary. AU Encounter Record Summary is designed to be compatible with the RESTful data access in IPA, e.g. AU Encounter Record Summary conformant data and AU Encounter Record Summary documents can be accessed by an IPA conformant client.
{:.grid}
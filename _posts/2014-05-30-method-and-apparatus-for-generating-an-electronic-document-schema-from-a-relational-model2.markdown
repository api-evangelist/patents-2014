---

title: Method and apparatus for generating an electronic document schema from a relational model
abstract: Methods and apparatus for generating a schema for data asset information are disclosed. In one example, complex type information corresponding to a logical relational data model that defines an organization of the data asset information is accessed. The logical relational data model includes a parent entity and child entities corresponding to the parent entity. Treating the complex type information produces scrubbed complex type information. The treatment of the complex type information includes, at least, the removal of foreign keys from child entities. The scrubbed complex type information is then translated to produce a hierarchical data model corresponding to the logical relational data model. A schema is then generated for the data asset information based upon the hierarchical data model.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09652478&OS=09652478&RS=09652478
owner: Fannie Mae
number: 09652478
owner_city: Washington
owner_country: US
publication_date: 20140530
---
This application relates generally to generating electronic document schemas and more specifically to generating an electronic document schema from a relational model.

Methods and apparatus for generating a schema for data asset information are disclosed. In one example complex type information corresponding to a logical relational data model that defines an organization of the data asset information is accessed. One example of a data asset is a collateral asset. The logical relational data model includes a parent entity and child entities corresponding to the parent entity. Treating the complex type information produces scrubbed complex type information. The treatment of the complex type information includes at least the removal of foreign keys from child entities. The scrubbed complex type information is then translated to produce a hierarchical data model corresponding to the logical relational data model. A hierarchical schema is then generated for the collateral asset information based upon the relational data model.

The present invention can be embodied in various forms including business processes computer implemented methods computer program products computer systems and networks user interfaces application programming interfaces and the like.

In the following description for purposes of explanation numerous details are set forth such as flowcharts and system configurations in order to provide an understanding of one or more embodiments of the present invention. However it is and will be apparent to one skilled in the art that these specific details are not required in order to practice the present invention.

According to one aspect this application provides a process for building common XML schemas such as those corresponding to logical data models of an enterprise. In the example of an enterprise the common XML scheme may be referred to as an Enterprise Common Format ECF . These ECFs are to act as the primary containers for data in motion across the enterprise.

The basic approach entails a top down analysis of the data model identifying the lowest level entities in the relational model and then moving up the chain to build the parent child relationship with the necessary constraints and cardinality at each level.

It should be appreciated that interpreting the logical model correctly plays a significant role in the design of the XML schema. Understanding the business process architecture can greatly enhance and optimize the quality of the schema. Careful analysis of the relational data model is the starting point in identifying the building blocks of the corresponding XML schema. This includes recognizing the atomic entities leaf nodes the intermediate entities and finally the top level entities. It is also useful to identify references to entities that may not be part of the core model being worked on.

5. The Financial Instrument Party and Agreement Type are external to the core definition of collateral asset .

6. The 1 N relationship between Party and Collateral Assets or Agreement Type and Collateral Assets signifies that the Party or Agreement Type schema will have repeating reference to the collateral object. A collateral asset schema should provision a placeholder for these foreign keys.

Building an XML schema based on this model thus implements the following building blocks in the design 

Before further description of the details of building the schema it is helpful to understand the basic mechanism involved in translating a relational model into a hierarchical model. If one looks closely at the logical data model in it is clear that each of the collateral subtypes carry necessary foreign keys which is an important ingredient for referential integrity in the relational model. However in a hierarchical model such a relationship is implicit in the parent child relationship. This concept is described further below.

Although a variety of design patterns may be implemented in accordance with this description in the presently described example the schema design pattern is referred to as the Venetian Blind pattern. In this pattern all the basic building blocks are defined as complex types with one root element holding the tree together.

It is evident from the model that at least three base complex types should be defined in this example they are named CashDetailType SecurityDetailType and LineOfCreditDetailType. The next step is to determine what attributes to put in each of these base complex types. Here in lieu of making a copy of all the attributes from the data model the unique attributes in each of the base complex types will be identified. The hierarchical model eliminates the need to duplicate keys and other common attributes and facilitates encapsulation in parent containers.

With reference to the logical data model all the attributes that are marked foreign key FK and some other common attributes like Data Source Identifier Collateral Report Date Account Number etc. may be moved to a higher level container.

In the case of CashDetailType this leaves one unique attribute Cash Amount to define the type. SecurityDetailType and LOCDetailType are also illustrated each having several attributes.

Moving one step up the hierarchy a complex type called CollateralDetailType serves as the container with a choice for one of the base types. This is necessary since at any given point in time a collateral asset can only be of one type.

Finally a super complex type that holds all the common attributes and a link to the CollateralDetailType is defined here it is called Collateral Type . This is the top level type that models the XML representation of the collateral asset data.

With this understanding of an example of a logical data model and corresponding graphical XML schema and text XML schema an aspect of automatically generating a schema from a logical data model is now further described.

Before proceeding with the discussion it should be noted that although certain attribute names are used in this description such names may be varied according to the practices adopted by the enterprise implementing schema generation in accordance with this description. The generally accepted practice is to align with the naming standards of the logical data model. However since these schemas represent data in motion and attribute names build the tags the schema designers often have to be mindful about payload size and impact on performance accordingly deviation in labeling can be expected.

In building an Enterprise Common Format ECF from a logical model it is important to codify and automate the process to ensure repeatability traceability and hence quality. At a minimum attribute and entity level compliance with the logical model should be guaranteed to the extent possible. Also the change management process should be configured so that it is relatively straightforward and convenient.

Initially the logical model information is accessed . This may be in the form of a logical model data file that is generated and saved as a particular file type by conventional logical modeling software. The logical model file may be established as a result of comprehensive collaboration within an enterprise to determine the constituent components of the logical relational model file such as the example depicted in and described above.

The process continues with extraction of complex type information from the logical model information. Examples of complex data types that are extracted from the logical model information are also described above in connection with . In one embodiment Embarcadero s ERSStudio XML export facility may be used to extract entities as the complex type information.

The complex type information is then scrubbed to produce a dataset that can be translated into hierarchical model information. The scrubbing process adds any necessary namespace information replaces data types to conform to target standards removes foreign keys from child entities and otherwise prepares the dataset for translation. Additional details regarding the scrubbing criteria are described further below. The scrubbing process creates a schema file comprising the atomic entities as defined in the data model. The translation process then translates the relational model to a hierarchical model according to defined relationships between them that are reflected in program code executable to carry out the translation. The final schema is then generated from the hierarchical model information.

The schema is used for a variety of concrete processes including the validation of electronic documents i.e. ensuring that an electronic document that has been or will be used in a transaction meets the requirements of the schema or for various quality control procedures during the preparation or use of electronic documents. A preferred example is financial transactions as described herein.

The electronic document schema generation application is hosted by a computing device that includes a processor and memory . The application is comprised of program code that may be stored in the memory for execution by the processor to carry out the functionality described herein. The application may also be stored on various computer readable media. Although the application is preferably provided as software it may alternatively be provided as hardware or firmware or any combination of hardware firmware and or software. Additionally although the application is illustrated as including certain modules the functionality may be provided using greater fewer or differently named modules.

As noted above the application includes program code for providing the functionality described herein. In one example this is carried out using meta language defined according to schemas as described herein. The following functions are provided 

2. Foreign key scrubbing from child entities relational data models require foreign key identification for relational integrity but implicit parent child relationship in a hierarchical XML model renders that redundant and unnecessary.

The meta language is used for the scrubbing functionality and for building the relationship hierarchy between entities for the defined subject matter. The complete schemas defining the meta language are respectively provided in Appendix A and Appendix B.

Some examples of meta language based definitions are provided below to illustrate examples of use cases.

1. Define data type translation literal e.g. any occurrence of a string maxOccurs 1 minOccurs 1 is replaced with an empty string 

2. Define data type translation functional e.g. a predefined function is executed when the defined string is encountered 

3. Foreign key substitution e.g. this definition indicates that the attribute named SecurityCUSIPIdentifier should be scrubbed from all entities other than the one defined as the PrimaryEntityName 

4. Entity merge e.g. the following merges the child entity into the parent creating one primary entity 

5. Complex type definition with Choice construct e.g. the following sets up the two child entities as an exclusive choice construct under the parent thereby defining another sub complex type 

6. Versioned root complex type definition e.g. a complex type defining a root element and carrying a version attribute is defined as follows 

Scrubbing the exported schema file comprised of complex type information is also carried out by the program code e.g. a Java program . The program code preferably includes the following elements 

c. A utility tool for scrubbing the complex type information to produce schemas that are compliant with the target design standards and data types. For example this utility may be run on the complex type information output from ER Studio to generate a schema that contains the base complex types corresponding to the logical entities in the data model.

d. A utility to generate the final XML schema based on the hierarchical relationship described in a configuration file using the meta language described above.

The following user configurable variables are also established in connection with accessing the logical model information and complex type information as well as scrubbing and translation.

 complete this section based on the data types defined in the logical model. Typically based upon existing template.

 identifies the entities where the primary keys are required the scrubbing process removes the foreign key references from the child entities.

 if entities from the logical model require to be merged in the final schema to reduce unnecessary XML graph depth define such merges in this section.

The translation portion is an important function of the tool where it interprets the configuration as described using the meta language and produces the final schema document that is in compliance with XML schema grammar. The translation process intelligently builds the intermediate super types and strings them together to produce the final tree.

Thus embodiments of the present invention produce and provide automatically generating electronic document schema from source logical model. Although the present invention has been described in considerable detail with reference to certain embodiments thereof the invention may be variously embodied without departing from the spirit or scope of the invention. Therefore the following claims should not be limited to the description of the embodiments contained herein in any way.


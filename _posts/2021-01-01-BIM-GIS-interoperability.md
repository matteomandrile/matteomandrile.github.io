---
layout: post
title: "BIM as a multiscale facilitator for built environment analysis"
author: "Matteo Mandrile"
categories: research
tags: [BIM]
city: Ljubljana
image: projects/2019-arc-it-cf/2019-arc-it-cf-ico.svg
---
The way we design, build, and manage our cities is undergoing a digital revolution. At the heart of this transformation is **Building Information Modeling (BIM)**, a powerful tool that extends beyond simply creating visually appealing 3D models. My research examines how BIM can serve as a **multiscale facilitator** for understanding the complex relationship between individual buildings and the sprawling urban environment.

## The Challenge: Connecting Digital Models of Buildings and Cities 
Imagine trying to understand a forest by only looking at individual trees or vice versa. It's tough. The same challenge exists in the built environment. We have incredibly detailed digital data for individual buildings (thanks to BIM) and broad urban data (from Geographic Information Systems, or GIS), but getting these two scales to "talk" to each other effectively is a significant hurdle.

![Data models and analyses for multiscale assessment](/assets/img/projects/2021-res-sl-mt/2021-res-sl-mt-data-models.svg "Data models and analyses for multiscale assessment")
*Data models and analyses for multiscale assessment.*

The core problem lies in **interoperability** – how different software and processes exchange information across these varying spatial scales. My research aimed to tackle this by:
- Facilitating multiscale data exchange using Building Information Modeling (BIM) tools and processes.
- Developing innovative data integration strategies.
- Highlighting the critical challenges and obstacles encountered along the way.

## The Approach: Literature and a Real-World Case Study
To achieve these goals, I combined a thorough **literature review** with a practical **case study** in collaboration with the Slovenian architectural firm Enota. This allowed me not only to understand the theoretical landscape but also to test my hypotheses in a real-world scenario.
My work broadly covers:
- A summary of sustainable policies in Europe, particularly focusing on the "Clean Energy for all Europeans Package" from 2019, which significantly revised the **Energy Performance of Building Directive**.
- An overview of analytical approaches spanning different scales.
- An evaluation of various data schemas and workflows.
- Two Practical Applications of Multiscale Data Integration.

## Navigating Data Standards: IFC vs. CityGML
A crucial part of bridging the building-city gap involves understanding and integrating different data standards. My research honed in on two key players: **CityGML** (for urban models) and **IFC** (Industry Foundation Classes) (for building models).

![Similarities and discrepancies between IFC and CityGML](/assets/img/projects/2021-res-sl-mt/2021-res-sl-mt-ifc-citygml.svg "Similarities and discrepancies between IFC and CityGML")
*Similarities and discrepancies between IFC and CityGML.*

While both standards share a similar core structure, they have distinct characteristics. For instance, IFC files are typically application-specific subsets (called Model View Definitions). In contrast, CityGML can be a subset by defining a "profile."
When it comes to **energy analysis**:
- **CityGML** uses an **Energy Application Domain Extension (ADE)** to capture domain-specific information, extending its core schema with relevant classes and attributes.
- **IFC** introduced an Information Delivery Manual in 2020, which led to the development of a Model View Definition specifically for building energy analysis.

Despite these advancements, a significant challenge remains: **the differences in data schema**. Both standards can represent buildings, but their internal structures vary. IFC, for example, excels at representing fine-scale building components, while CityGML handles objects at a coarser resolution. This disparity often makes direct data translation difficult, with many IFC classes lacking a direct equivalent in CityGML.

## City Information Modeling (CIM): A Framework for Integration
To overcome these integration challenges, researchers have proposed a framework called **City Information Modeling (CIM)**. The idea is to extract building data from BIM and urban data from GIS and then combine them to create a holistic urban model.
My research explored a workflow for multiscale information integration that involves:
1. Exporting BIM data (in IFC and Excel formats).
2. Restructuring this data to match the CityGML schema.
3. Storing the output in an urban database for various applications.

## Case Study 1: Building a Semantic Urban Model (Top-Down Approach)
In Ljubljana, Slovenia, I employed a "top-down" approach to develop a **semantic urban model** for two central neighborhoods utilizing institutional open data. This involved creating a Service-Oriented Architecture (SOA) system to manage the creation and use of the 3D city model.
The process included creating a three-tier **Service-Oriented Architecture** system composed by:
- **Data Layer:** Storing information in a spatial database managed with PostgreSQL.
- **Middleware Layer:** Controlling interactions between the application and data layers.
- **Application Layer:** Defining visualization use cases on web browsers (using WebGL) and local computers (with Google Earth).

For the modeling itself, I combined GIS shapefiles and Lidar data with an open-source algorithm called **3dfier** (developed at TU Delft) to reconstruct 3D models from 2D GIS datasets. Once the 3D reconstruction was complete, the model was imported into the database and enriched with building attributes. This allowed for effective data management, querying, and export for various applications, including visualization in Google Earth and interactive web browsers.
While the CityGML model could be enriched for energy analysis using the Energy ADE classes, a significant obstacle was the availability of data. Much of the crucial energy performance data was in non-machine-interpretable PDF formats, making automated enrichment difficult.

## Case Study 2: Integrating Building and City Data (Bottom-Up Approach)
The second case study involved a "bottom-up" data integration approach for the renovation and extension of the historic Hotel Bellevue in Ljubljana. This project, designed by Enota, involved transforming an abandoned cultural heritage site into a modern facility with energy-saving principles.
This approach focused on several information exchanges:
- Between BIM and **Building Energy Models (BEM)**.
- Between IFC and CityGML.

The three key steps were:
1. **Enrichment of the BIM model** with the requirements for a BEM.
2. **Energy demand assessment** to evaluate building energy loads (though reliable values were not yet available at this stage).
3. **Data integration** to enrich a CityGML database with information from the IFC models.

To extract, transform, and load information between the different schemas, I used **FME**, a powerful data conversion tool. This allowed us to extract and reorganize data from IFC according to the CityGML schema. While the process was generally successful for basic geometry and attributes, handling domain-specific information proved more complex due to the differing hierarchical configurations of the data models.

## The Path Forward: Unlocking the Full Potential
My research confirms that **multiscale analysis of the built environment is possible, albeit with some limitations**. Data integration strategies are key to facilitating software interoperability. However, actual progress hinges on the following:
- **Stakeholder agreement on standard definitions** for semantic modeling.
- **Standardization** of the entire process, including clearly defined roles and responsibilities.
- **Understanding data schemas** is paramount for seamless digital information exchange. As the saying goes, "Do once, use many" – a well-structured workflow can be repeated and scaled.

## Recommendations for the Future:
To truly unlock the potential of BIM for urban analysis, I recommend:
- Further research into **the harmonization of data models** and collaborative procedures within the AEC (Architecture, Engineering, and Construction) field.
- A concerted effort towards **uniform standardization for environmental analyses**.
- **Public bodies should strive to make energy data available in open, machine-readable formats**.

## Exciting Future Applications:
The implications of this research are vast and exciting! Imagine:
- **Digital Building Permits:** Practitioners could instantly access 3D contextual and semantic urban regulatory data from a city model. Public employees could then verify designs against urban standards and seamlessly update the model with "as-built" information.
- **Decision-Making Tools:** Powerful tools could be developed to assess new urban developments or evaluate the effectiveness of urban energy policies.

By bridging the gap between building-scale and city-scale data, we can create more innovative, sustainable, and resilient urban environments for the future.
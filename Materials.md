- [Home](/Biofabrication-Design-Project/index)
- [Mechanical](/Biofabrication-Design-Project/Mechanical)
- [Electrical](/Biofabrication-Design-Project/Electrical)
- [Software](/Biofabrication-Design-Project/Software)
- **[Materials](/Biofabrication-Design-Project/Materials)**
- [Cells](/Biofabrication-Design-Project/Cells)

# Materials

The choice of cell-encapsulating tissue matrix materials presented several constraints in the context of in-situ skin bioprinting. Due to the relatively simple bilayered structure of the tissue printed, and the critically time-sensitive nature of the wounds and ulcers treated using this method, rapidity of extrusion was taken to be a priority in materials design. Achieving the goal of printing the tissue replacement in-situ effectively excluded some methods of post-extrusion processing such as temperature reduction and initiator exposure, as well as underlined the need for stringent biocompatibility standards, as there is no chance to review the printed construct before it is applied to the patient.


Ultimately, a fibrinogen-thrombin enzymatic crosslinking system was chosen for both the epidermal and dermal layers, with both the fibroblast-containing dermal component and the keratinocyte-containing epidermal components being fibrinogen-based and the thrombin component mixed in during printing to initiate crosslinking and enable the sol-gel transition. Fibrinogen is a chemical component of human blood that allows it to form a clot when a wound is created and it is exposed to its cross-linking enzyme, thrombin. The use of this system mimics the natural process of wound healing and, unlike photoinitiated crosslinking of synthetic biomaterials with methacrylate groups, allows for the unhindered use of chemoattractants and other desired construct additives at low concentrations without leading to undesired side reactions and reduced efficacy. Additionally, the use of the fibrinogen-thrombin system for closing surgical wounds has been demonstrated commercially as [Tisseel](https://advancedsurgery.baxter.com/products/tisseel#:~:text=Mechanism%20of%20Action.%20Upon%20mixing%20Sealer%20Protein%20%28Human%29,has%20all%20relevant%20components%20to%20form%20a%20clot.), and its use for skin tissue repair has been investigated in animal research studies (such as [this study by Albanna et al.)](https://pubmed.ncbi.nlm.nih.gov/30755653/)


The kinetics of the fibrinogen-thrombin crosslinking reaction are complex, described using a modified Michaelis-Menten scheme in which the order of the reaction in the substrate varies depending on its concentration range. [(Shinowara)](https://www.sciencedirect.com/science/article/pii/S0926659366800759) However, at the concentrations used in bioprinting, the reaction proceeds to a level of gelation capable of supporting the following layer within approximately fifteen seconds after extrusion using a static mixer. With the determined extrusion rate of 1.1x10^-4 mL/s, this reaction time is not expected to negatively impact the rapid three-dimensional construction of the tissue replacement.


To determine the maximum flow rate achievable while maintaining a minimum threshold of 70% cell viability, shear stress calculations were performed using a previously developed Python tool and approximations of fluid characteristics. The maximum shear stress tolerable at the nozzle walls to maintain sufficient cell viability was determined to be 0.3 Pa due to the finding that keratinocytes underwent significant disruptions to their function at a tested stress of 0.6 Pa. [(Agarwal et al.)](https://pubmed.ncbi.nlm.nih.gov/30969461/) While the Hagen-Poiseulle equation is frequently used to determine relationships between pressure drop and flow rate for Newtonian fluids (the shear stress profiles for which can subsequently be determined using the Newtonian shear stress equation), the strongly non-Newtonian characteristics of biological fluids necessitated a more computationally intensive approximation. Changes in fluid characteristics due to reactions within the nozzle were ignored, and the Carreau-Yasuda model constants for human blood [(obtained by Biasetti et al.)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3163425/) were used to approximate the characteristics of the extruded solution due to similarities in chemical components and cell content. 


This model was developed by Müller et al. with the specific application of bioprinting in mind. The assumptions made by the authors to solve fluid flow equations include a cylindrical channel shape, a no-slip boundary condition, and a continuous shear rate. [(Müller et al.)](https://journals-plos-org.proxy.library.vanderbilt.edu/plosone/article?id=10.1371/journal.pone.0236371) However, the double-barreled syringe model used to mix the fibrinogen-containing and thrombin-containing components introduces some complexity into extrusion flow characteristics that is not fully accounted for by the model. Since cell viability is affected by the highest level of shear stress the cells experience as they travel through the length of the syringe, the smallest nozzle internal diameter of 2mm was used as a basis for determining the maximum shear stress and viability-affecting shear stress profile (since viscosity changes due to reactions are not considered.) The total flow rate of the mixed, extruded gel is therefore twice that determined as maximum within the Python calculations. Using this 2mm basis, the maximum flow rate of the fibrinogen-cellular gel component through the internal nozzle was determined to be 5.5x10^-5 mL/s. Relevant inputs were (flow rate, channel size, code conditions) The plot of shear stress versus distance from nozzle axis is shown below:


![Shear Stress Profile](/shear-stress-profile-s21.png)


The total volumetric flow rate extruded from the 6mm exterior nozzle is therefore twice this value, or 1.1x10^-4 mL/s.


Utilizing Good Manufacturing Practices, or GMPs, during the manufacture and use of both the device and its chemical and cellular components is essential for maintaining both safety and regulatory approval for the process. While cells and chemical components will be purchased from outside suppliers with their own regulatory requirements, the mixing of appropriate concentrations of viable cells into the fibrinogen-containing gel components would be a type of manufacturing process governed by GMP standards. Adhering to GMPs requires establishing standard processes and protocols for manufacturing, maintaining stringent quality control through qualitative testing, and the training of equipment operators to maintain cleanliness and uphold procedure during manufacturing. [(SafetyCulture)](https://safetyculture.com/topics/gmp/) Specifically for this application, the storage and transport process of the cell-containing gel components would likely need to be assessed for the maintenance of cell viability through viability assays. The fluid mechanics properties of the final gel components would also need to be verified in order to assure proper dispensation rates in conjunction with the final bioplotter design. The monetary cost of facility inspection, quality verification, and process refinement can vary widely with the scale and scope of a manufacturing project, but GMP regulatory approval is necessary to ensure the legality and safety of the product’s development and medical use. [FDA](https://www.fda.gov/drugs/pharmaceutical-quality-resources/facts-about-current-good-manufacturing-practices-cgmps)



Citations

[Tisseel Product Overview](https://advancedsurgery.baxter.com/products/tisseel#:~:text=Mechanism%20of%20Action.%20Upon%20mixing%20Sealer%20Protein%20%28Human%29,has%20all%20relevant%20components%20to%20form%20a%20clot.)


[Albanna et al. In Situ Bioprinting of Autologous Skin Cells Accelerates Wound Healing of Extensive Excisional Full-Thickness Wounds](https://pubmed.ncbi.nlm.nih.gov/30755653/)


[Shinowara. Kinetics of Fibrinogen-Thrombin Reaction](https://www.sciencedirect.com/science/article/pii/S0926659366800759)


[Agarwal et al. Keratinocytes' Response to Stress Source](https://pubmed.ncbi.nlm.nih.gov/30969461/)


[Biasetti et al. Carreau-Yasuda Parameters for Human Blood](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3163425/)


[Muller et al. Shear Stress Model Source](https://journals-plos-org.proxy.library.vanderbilt.edu/plosone/article?id=10.1371/journal.pone.0236371)


[SafetyCulture: GMP Overview](https://safetyculture.com/topics/gmp/)


[FDA: GMP Overview](https://www.fda.gov/drugs/pharmaceutical-quality-resources/facts-about-current-good-manufacturing-practices-cgmps)

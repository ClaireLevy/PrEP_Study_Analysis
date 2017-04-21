PrEP Study Microarray Analysis
================
Claire Levy

Experimental set up
-------------------

We isolated RNA from four different sample types from 8 donors pre- and post- initiation of prEP. The pre-initation was called "Enrollment" and the post-initiation visit was called "Visit2"

Sample Types

-   Duodenal biopsy
-   Rectal biopsy
-   PAXgene (whole blood collected into RNA preservative)
-   PBMC (PBMC isolated from whole blood)

Plots of non-normalized data

![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/nonnormalized%20data-1.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/nonnormalized%20data-2.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/nonnormalized%20data-3.png)

These normalized samples all look... normal.

![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-1.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-2.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-3.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-4.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-5.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-6.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-7.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-8.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-9.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-10.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-11.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-12.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-13.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-14.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-15.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-16.png)

Non-specific filtering
----------------------

I will filter out any probes that are not expressed above the 0.05 p-value cut-off in at least 6 samples. I chose 6 because a probe may not be expressed at all in the 8 Enrollment samples (so 0/16 total), but may show up at Visit2 (8 possibilities). It would still be biologically interesting if a probe was expressed at Visit2 (and not at enrollment) even if it wasn't in all donors, so I'll require it to show up in at least 6 of them.

Number of probes removed from the data sets after filtering for expression. All started with 47323 probes.

<table style="width:44%;">
<colgroup>
<col width="9%" />
<col width="12%" />
<col width="9%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">Duod</th>
<th align="center">Rectal</th>
<th align="center">PBMC</th>
<th align="center">PAXgene</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">26818</td>
<td align="center">26787</td>
<td align="center">28427</td>
<td align="center">30127</td>
</tr>
</tbody>
</table>

Number of DE probes for each contrast
-------------------------------------

The Duodenal samples were the only ones with any differentially expressed probes. There were 76 downregulated probes and 15 upregulated probes.

Changes in the Duodenum pre vs post-prEP
----------------------------------------

<table>
<colgroup>
<col width="17%" />
<col width="15%" />
<col width="52%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">TargetID</th>
<th align="center">Direction</th>
<th align="center">DEFINITION</th>
<th align="center">adj.P.Val</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">GK</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens glycerol kinase (GK), transcript variant 2, mRNA.</td>
<td align="center">0.006903</td>
</tr>
<tr class="even">
<td align="center">LCT</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens lactase (LCT), mRNA.</td>
<td align="center">0.006903</td>
</tr>
<tr class="odd">
<td align="center">GK</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens glycerol kinase (GK), transcript variant 1, mRNA.</td>
<td align="center">0.006903</td>
</tr>
<tr class="even">
<td align="center">LAMA3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens laminin, alpha 3 (LAMA3), transcript variant 1, mRNA.</td>
<td align="center">0.006903</td>
</tr>
<tr class="odd">
<td align="center">DFNA5</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens deafness, autosomal dominant 5 (DFNA5), transcript variant 1, mRNA.</td>
<td align="center">0.006903</td>
</tr>
<tr class="even">
<td align="center">MGC13057</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens hypothetical protein MGC13057 (MGC13057), mRNA.</td>
<td align="center">0.006903</td>
</tr>
<tr class="odd">
<td align="center">AQP10</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens aquaporin 10 (AQP10), mRNA.</td>
<td align="center">0.01219</td>
</tr>
<tr class="even">
<td align="center">SLC36A1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens solute carrier family 36 (proton/amino acid symporter), member 1 (SLC36A1), mRNA.</td>
<td align="center">0.01347</td>
</tr>
<tr class="odd">
<td align="center">KIAA1671</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens KIAA1671 protein (KIAA1671), mRNA.</td>
<td align="center">0.01347</td>
</tr>
<tr class="even">
<td align="center">UGT2B11</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens UDP glucuronosyltransferase 2 family, polypeptide B11 (UGT2B11), mRNA.</td>
<td align="center">0.0173</td>
</tr>
<tr class="odd">
<td align="center">TREH</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens trehalase (brush-border membrane glycoprotein) (TREH), mRNA.</td>
<td align="center">0.01853</td>
</tr>
<tr class="even">
<td align="center">LOC653117</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens similar to B7h.4 (LOC653117), mRNA.</td>
<td align="center">0.01853</td>
</tr>
<tr class="odd">
<td align="center">SLC44A2</td>
<td align="center">UP</td>
<td align="center">Homo sapiens solute carrier family 44, member 2 (SLC44A2), mRNA.</td>
<td align="center">0.01952</td>
</tr>
<tr class="even">
<td align="center">S100G</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens S100 calcium binding protein G (S100G), mRNA.</td>
<td align="center">0.01952</td>
</tr>
<tr class="odd">
<td align="center">PPP1R1B</td>
<td align="center">UP</td>
<td align="center">Homo sapiens protein phosphatase 1, regulatory (inhibitor) subunit 1B (dopamine and cAMP regulated phosphoprotein, DARPP-32) (PPP1R1B), transcript variant 2, mRNA.</td>
<td align="center">0.01952</td>
</tr>
<tr class="even">
<td align="center">SERPINA1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens serpin peptidase inhibitor, clade A (alpha-1 antiproteinase, antitrypsin), member 1 (SERPINA1), transcript variant 3, mRNA.</td>
<td align="center">0.01952</td>
</tr>
<tr class="odd">
<td align="center">C16ORF33</td>
<td align="center">UP</td>
<td align="center">Homo sapiens chromosome 16 open reading frame 33 (C16orf33), mRNA.</td>
<td align="center">0.01952</td>
</tr>
<tr class="even">
<td align="center">SERPINA1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens serpin peptidase inhibitor, clade A (alpha-1 antiproteinase, antitrypsin), member 1 (SERPINA1), transcript variant 2, mRNA.</td>
<td align="center">0.01952</td>
</tr>
<tr class="odd">
<td align="center">MUPCDH</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens mucin-like protocadherin (MUPCDH), transcript variant 1, mRNA.</td>
<td align="center">0.01952</td>
</tr>
<tr class="even">
<td align="center">CD36</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens CD36 molecule (thrombospondin receptor) (CD36), transcript variant 3, mRNA.</td>
<td align="center">0.01983</td>
</tr>
<tr class="odd">
<td align="center">ENPP7</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens ectonucleotide pyrophosphatase/phosphodiesterase 7 (ENPP7), mRNA.</td>
<td align="center">0.02131</td>
</tr>
<tr class="even">
<td align="center">ABHD5</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens abhydrolase domain containing 5 (ABHD5), mRNA.</td>
<td align="center">0.02144</td>
</tr>
<tr class="odd">
<td align="center">LOC653381</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens similar to Sorbitol dehydrogenase (L-iditol 2-dehydrogenase) (LOC653381), mRNA.</td>
<td align="center">0.02244</td>
</tr>
<tr class="even">
<td align="center">SLC2A5</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens solute carrier family 2 (facilitated glucose/fructose transporter), member 5 (SLC2A5), mRNA.</td>
<td align="center">0.02244</td>
</tr>
<tr class="odd">
<td align="center">EDN3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens endothelin 3 (EDN3), transcript variant 3, mRNA.</td>
<td align="center">0.02244</td>
</tr>
<tr class="even">
<td align="center">TSHZ1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens teashirt zinc finger homeobox 1 (TSHZ1), mRNA.</td>
<td align="center">0.02303</td>
</tr>
<tr class="odd">
<td align="center">SORD</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens sorbitol dehydrogenase (SORD), mRNA.</td>
<td align="center">0.02326</td>
</tr>
<tr class="even">
<td align="center">BTNL8</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens butyrophilin-like 8 (BTNL8), transcript variant 1, mRNA.</td>
<td align="center">0.02834</td>
</tr>
<tr class="odd">
<td align="center">SEPP1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens selenoprotein P, plasma, 1 (SEPP1), transcript variant 1, mRNA.</td>
<td align="center">0.02834</td>
</tr>
<tr class="even">
<td align="center">CLIC6</td>
<td align="center">UP</td>
<td align="center">Homo sapiens chloride intracellular channel 6 (CLIC6), mRNA.</td>
<td align="center">0.02834</td>
</tr>
<tr class="odd">
<td align="center">AQP7P2</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens aquaporin 7 pseudogene 2 (AQP7P2), non-coding RNA.</td>
<td align="center">0.02834</td>
</tr>
<tr class="even">
<td align="center">PCK1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens phosphoenolpyruvate carboxykinase 1 (soluble) (PCK1), mRNA.</td>
<td align="center">0.02834</td>
</tr>
<tr class="odd">
<td align="center">LCT</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens lactase (LCT), mRNA.</td>
<td align="center">0.02834</td>
</tr>
<tr class="even">
<td align="center">SHBG</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens sex hormone-binding globulin (SHBG), mRNA.</td>
<td align="center">0.02834</td>
</tr>
<tr class="odd">
<td align="center">MST1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens macrophage stimulating 1 (hepatocyte growth factor-like) (MST1), mRNA.</td>
<td align="center">0.02834</td>
</tr>
<tr class="even">
<td align="center">RIOK3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens RIO kinase 3 (yeast) (RIOK3), mRNA.</td>
<td align="center">0.02834</td>
</tr>
<tr class="odd">
<td align="center">GOLPH4</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens golgi phosphoprotein 4 (GOLPH4), mRNA.</td>
<td align="center">0.02834</td>
</tr>
<tr class="even">
<td align="center">ENPP7</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens ectonucleotide pyrophosphatase/phosphodiesterase 7 (ENPP7), mRNA.</td>
<td align="center">0.02975</td>
</tr>
<tr class="odd">
<td align="center">HIST2H2BE</td>
<td align="center">UP</td>
<td align="center">Homo sapiens histone cluster 2, H2be (HIST2H2BE), mRNA.</td>
<td align="center">0.02975</td>
</tr>
<tr class="even">
<td align="center">LAMA3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens laminin, alpha 3 (LAMA3), transcript variant 1, mRNA.</td>
<td align="center">0.02986</td>
</tr>
<tr class="odd">
<td align="center">ASAH2</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens N-acylsphingosine amidohydrolase (non-lysosomal ceramidase) 2 (ASAH2), mRNA.</td>
<td align="center">0.03038</td>
</tr>
<tr class="even">
<td align="center">SCG5</td>
<td align="center">UP</td>
<td align="center">Homo sapiens secretogranin V (7B2 protein) (SCG5), mRNA.</td>
<td align="center">0.03038</td>
</tr>
<tr class="odd">
<td align="center">AQP11</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens aquaporin 11 (AQP11), mRNA.</td>
<td align="center">0.03102</td>
</tr>
<tr class="even">
<td align="center">PROM2</td>
<td align="center">UP</td>
<td align="center">Homo sapiens prominin 2 (PROM2), mRNA.</td>
<td align="center">0.03274</td>
</tr>
<tr class="odd">
<td align="center">AKR7A3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens aldo-keto reductase family 7, member A3 (aflatoxin aldehyde reductase) (AKR7A3), mRNA.</td>
<td align="center">0.03274</td>
</tr>
<tr class="even">
<td align="center">BEND7</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens BEN domain containing 7 (BEND7), transcript variant 2, mRNA.</td>
<td align="center">0.03319</td>
</tr>
<tr class="odd">
<td align="center">TM4SF20</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens transmembrane 4 L six family member 20 (TM4SF20), mRNA.</td>
<td align="center">0.03319</td>
</tr>
<tr class="even">
<td align="center">ASAH2</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens N-acylsphingosine amidohydrolase (non-lysosomal ceramidase) 2 (ASAH2), mRNA.</td>
<td align="center">0.03319</td>
</tr>
<tr class="odd">
<td align="center">SPDEF</td>
<td align="center">UP</td>
<td align="center">Homo sapiens SAM pointed domain containing ets transcription factor (SPDEF), mRNA.</td>
<td align="center">0.03319</td>
</tr>
<tr class="even">
<td align="center">LOC653308</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens similar to N-acylsphingosine amidohydrolase 2, transcript variant 1 (LOC653308), mRNA.</td>
<td align="center">0.03319</td>
</tr>
<tr class="odd">
<td align="center">CHN2</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens chimerin (chimaerin) 2 (CHN2), transcript variant 2, mRNA.</td>
<td align="center">0.03319</td>
</tr>
<tr class="even">
<td align="center">HLA-DRA</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens major histocompatibility complex, class II, DR alpha (HLA-DRA), mRNA.</td>
<td align="center">0.03319</td>
</tr>
<tr class="odd">
<td align="center">PHLPP2</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens PH domain and leucine rich repeat protein phosphatase 2 (PHLPP2), mRNA.</td>
<td align="center">0.03319</td>
</tr>
<tr class="even">
<td align="center">RIOK3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens RIO kinase 3 (yeast) (RIOK3), transcript variant 1, mRNA.</td>
<td align="center">0.03319</td>
</tr>
<tr class="odd">
<td align="center">CEACAM1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens carcinoembryonic antigen-related cell adhesion molecule 1 (biliary glycoprotein) (CEACAM1), transcript variant 1, mRNA.</td>
<td align="center">0.03319</td>
</tr>
<tr class="even">
<td align="center">CD36</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens CD36 molecule (thrombospondin receptor) (CD36), transcript variant 1, mRNA.</td>
<td align="center">0.03375</td>
</tr>
<tr class="odd">
<td align="center">SORD</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens sorbitol dehydrogenase (SORD), mRNA.</td>
<td align="center">0.03375</td>
</tr>
<tr class="even">
<td align="center">SLC2A12</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens solute carrier family 2 (facilitated glucose transporter), member 12 (SLC2A12), mRNA.</td>
<td align="center">0.03383</td>
</tr>
<tr class="odd">
<td align="center">HNF4G</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens hepatocyte nuclear factor 4, gamma (HNF4G), mRNA.</td>
<td align="center">0.03392</td>
</tr>
<tr class="even">
<td align="center">SLC23A1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens solute carrier family 23 (nucleobase transporters), member 1 (SLC23A1), transcript variant 1, mRNA.</td>
<td align="center">0.03504</td>
</tr>
<tr class="odd">
<td align="center">SORD</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens sorbitol dehydrogenase (SORD), mRNA.</td>
<td align="center">0.03586</td>
</tr>
<tr class="even">
<td align="center">SLC46A1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens solute carrier family 46 (folate transporter), member 1 (SLC46A1), mRNA.</td>
<td align="center">0.0361</td>
</tr>
<tr class="odd">
<td align="center">LAMB3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens laminin, beta 3 (LAMB3), transcript variant 1, mRNA.</td>
<td align="center">0.03736</td>
</tr>
<tr class="even">
<td align="center">C12ORF35</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens chromosome 12 open reading frame 35 (C12orf35), mRNA.</td>
<td align="center">0.03736</td>
</tr>
<tr class="odd">
<td align="center">HLA-DRB6</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens major histocompatibility complex, class II, DR beta 6 (pseudogene) (HLA-DRB6), non-coding RNA.</td>
<td align="center">0.03736</td>
</tr>
<tr class="even">
<td align="center">IL32</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens interleukin 32 (IL32), transcript variant 7, mRNA.</td>
<td align="center">0.03736</td>
</tr>
<tr class="odd">
<td align="center">TMEM198</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens transmembrane protein 198 (TMEM198), mRNA.</td>
<td align="center">0.03898</td>
</tr>
<tr class="even">
<td align="center">CPA2</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens carboxypeptidase A2 (pancreatic) (CPA2), mRNA.</td>
<td align="center">0.03898</td>
</tr>
<tr class="odd">
<td align="center">EDN3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens endothelin 3 (EDN3), transcript variant 2, mRNA.</td>
<td align="center">0.03993</td>
</tr>
<tr class="even">
<td align="center">HSH2D</td>
<td align="center">UP</td>
<td align="center">Homo sapiens hematopoietic SH2 domain containing (HSH2D), mRNA.</td>
<td align="center">0.03993</td>
</tr>
<tr class="odd">
<td align="center">IFI27L1</td>
<td align="center">UP</td>
<td align="center">Homo sapiens interferon, alpha-inducible protein 27-like 1 (IFI27L1), transcript variant 1, mRNA.</td>
<td align="center">0.04039</td>
</tr>
<tr class="even">
<td align="center">LY6E</td>
<td align="center">UP</td>
<td align="center">Homo sapiens lymphocyte antigen 6 complex, locus E (LY6E), mRNA.</td>
<td align="center">0.04039</td>
</tr>
<tr class="odd">
<td align="center">FLJ22675</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens hypothetical gene supported by AK026328 (FLJ22675), mRNA.</td>
<td align="center">0.04039</td>
</tr>
<tr class="even">
<td align="center">HLA-DPA1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens major histocompatibility complex, class II, DP alpha 1 (HLA-DPA1), mRNA.</td>
<td align="center">0.04086</td>
</tr>
<tr class="odd">
<td align="center">PLA2G4C</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens phospholipase A2, group IVC (cytosolic, calcium-independent) (PLA2G4C), mRNA.</td>
<td align="center">0.04086</td>
</tr>
<tr class="even">
<td align="center">HMOX1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens heme oxygenase (decycling) 1 (HMOX1), mRNA.</td>
<td align="center">0.0428</td>
</tr>
<tr class="odd">
<td align="center">C8G</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens complement component 8, gamma polypeptide (C8G), mRNA.</td>
<td align="center">0.0428</td>
</tr>
<tr class="even">
<td align="center">FOXQ1</td>
<td align="center">UP</td>
<td align="center">Homo sapiens forkhead box Q1 (FOXQ1), mRNA.</td>
<td align="center">0.0428</td>
</tr>
<tr class="odd">
<td align="center">ENPP3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens ectonucleotide pyrophosphatase/phosphodiesterase 3 (ENPP3), mRNA.</td>
<td align="center">0.0428</td>
</tr>
<tr class="even">
<td align="center">LOC100133583</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens similar to major histocompatibility complex, class II, DQ beta 1, transcript variant 2 (LOC100133583), mRNA.</td>
<td align="center">0.04317</td>
</tr>
<tr class="odd">
<td align="center">SUSD2</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens sushi domain containing 2 (SUSD2), mRNA.</td>
<td align="center">0.04384</td>
</tr>
<tr class="even">
<td align="center">OBFC2A</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens oligonucleotide/oligosaccharide-binding fold containing 2A (OBFC2A), mRNA.</td>
<td align="center">0.04384</td>
</tr>
<tr class="odd">
<td align="center">ASAH2</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens N-acylsphingosine amidohydrolase (non-lysosomal ceramidase) 2 (ASAH2), mRNA.</td>
<td align="center">0.04417</td>
</tr>
<tr class="even">
<td align="center">NPC1L1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens NPC1 (Niemann-Pick disease, type C1, gene)-like 1 (NPC1L1), mRNA.</td>
<td align="center">0.0446</td>
</tr>
<tr class="odd">
<td align="center">IGFBP2</td>
<td align="center">UP</td>
<td align="center">Homo sapiens insulin-like growth factor binding protein 2, 36kDa (IGFBP2), mRNA.</td>
<td align="center">0.04479</td>
</tr>
<tr class="even">
<td align="center">SLC7A7</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens solute carrier family 7 (cationic amino acid transporter, y+ system), member 7 (SLC7A7), mRNA.</td>
<td align="center">0.04509</td>
</tr>
<tr class="odd">
<td align="center">GUCA2B</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens guanylate cyclase activator 2B (uroguanylin) (GUCA2B), mRNA.</td>
<td align="center">0.04631</td>
</tr>
<tr class="even">
<td align="center">LOC642073</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens similar to MHC class II antigen (LOC642073), mRNA.</td>
<td align="center">0.04664</td>
</tr>
<tr class="odd">
<td align="center">IL32</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens interleukin 32 (IL32), transcript variant 4, mRNA.</td>
<td align="center">0.04664</td>
</tr>
<tr class="even">
<td align="center">IGFBP5</td>
<td align="center">UP</td>
<td align="center">Homo sapiens insulin-like growth factor binding protein 5 (IGFBP5), mRNA.</td>
<td align="center">0.04664</td>
</tr>
<tr class="odd">
<td align="center">C18ORF56</td>
<td align="center">UP</td>
<td align="center">Homo sapiens chromosome 18 open reading frame 56 (C18orf56), mRNA.</td>
<td align="center">0.04827</td>
</tr>
</tbody>
</table>

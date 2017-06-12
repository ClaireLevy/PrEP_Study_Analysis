PreP Study Microarray Analysis
================
Claire Levy

Experimental set up
-------------------

We isolated RNA from four different sample types from 8 donors pre- and post- initiation of PreP. The pre-initation was called "Enrollment" and the post-initiation visit was called "Visit2"

Sample Types

-   Duodenal biopsy
-   Rectal biopsy
-   PAXgene (whole blood collected into RNA preservative)
-   PBMC (PBMC isolated from whole blood)

NOTE: PTID BG2305 may not have been adherent, left them in for now. May have had problems refilling prescription on time.

### Plots of background-corrected but non-normalized data

![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/nonnormalized%20data-1.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/nonnormalized%20data-2.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/nonnormalized%20data-3.png)

These normalized samples all look good.

![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-1.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-2.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-3.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-4.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-5.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-6.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-7.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-8.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-9.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-10.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-11.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-12.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-13.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-14.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-15.png)![](PrEP_Study_Microarray_Analysis_files/figure-markdown_github/norm%20plots-16.png)

Non-specific filtering
----------------------

There are 8 donors x 1 tissue type x 2 timepoints = 16 samples in this set. I will filter out any probes that are not expressed above the 0.05 p-value cut-off in at least 7 samples. I chose 7 because a probe may not be expressed at all in the 8 Enrollment samples (so 0/16 total), but may show up at Visit2 (8 possibilities). It would still be biologically interesting if a probe was expressed at Visit2 (and not at enrollment) even if it wasn't in all donors, so I'll require it to show up in at least 7 of them.

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

The duodenal samples were the only ones with any differentially expressed probes. For Visit2 relative to enrollment, there were 70 down-regulated probes and 11 up-regulated probes.

Changes in the Duodenum pre vs post-PreP: logFC cutoff = 0.5, p-value cut-off = 0.05
------------------------------------------------------------------------------------

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
<td align="center">0.007008</td>
</tr>
<tr class="even">
<td align="center">LCT</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens lactase (LCT), mRNA.</td>
<td align="center">0.007008</td>
</tr>
<tr class="odd">
<td align="center">GK</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens glycerol kinase (GK), transcript variant 1, mRNA.</td>
<td align="center">0.007008</td>
</tr>
<tr class="even">
<td align="center">DFNA5</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens deafness, autosomal dominant 5 (DFNA5), transcript variant 1, mRNA.</td>
<td align="center">0.007008</td>
</tr>
<tr class="odd">
<td align="center">LAMA3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens laminin, alpha 3 (LAMA3), transcript variant 1, mRNA.</td>
<td align="center">0.007008</td>
</tr>
<tr class="even">
<td align="center">MGC13057</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens hypothetical protein MGC13057 (MGC13057), mRNA.</td>
<td align="center">0.007008</td>
</tr>
<tr class="odd">
<td align="center">AQP10</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens aquaporin 10 (AQP10), mRNA.</td>
<td align="center">0.0131</td>
</tr>
<tr class="even">
<td align="center">KIAA1671</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens KIAA1671 protein (KIAA1671), mRNA.</td>
<td align="center">0.01454</td>
</tr>
<tr class="odd">
<td align="center">SLC36A1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens solute carrier family 36 (proton/amino acid symporter), member 1 (SLC36A1), mRNA.</td>
<td align="center">0.01454</td>
</tr>
<tr class="even">
<td align="center">UGT2B11</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens UDP glucuronosyltransferase 2 family, polypeptide B11 (UGT2B11), mRNA.</td>
<td align="center">0.01959</td>
</tr>
<tr class="odd">
<td align="center">TREH</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens trehalase (brush-border membrane glycoprotein) (TREH), mRNA.</td>
<td align="center">0.01999</td>
</tr>
<tr class="even">
<td align="center">LOC653117</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens similar to B7h.4 (LOC653117), mRNA.</td>
<td align="center">0.01999</td>
</tr>
<tr class="odd">
<td align="center">S100G</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens S100 calcium binding protein G (S100G), mRNA.</td>
<td align="center">0.01999</td>
</tr>
<tr class="even">
<td align="center">PPP1R1B</td>
<td align="center">UP</td>
<td align="center">Homo sapiens protein phosphatase 1, regulatory (inhibitor) subunit 1B (dopamine and cAMP regulated phosphoprotein, DARPP-32) (PPP1R1B), transcript variant 2, mRNA.</td>
<td align="center">0.01999</td>
</tr>
<tr class="odd">
<td align="center">SERPINA1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens serpin peptidase inhibitor, clade A (alpha-1 antiproteinase, antitrypsin), member 1 (SERPINA1), transcript variant 3, mRNA.</td>
<td align="center">0.01999</td>
</tr>
<tr class="even">
<td align="center">SERPINA1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens serpin peptidase inhibitor, clade A (alpha-1 antiproteinase, antitrypsin), member 1 (SERPINA1), transcript variant 2, mRNA.</td>
<td align="center">0.02058</td>
</tr>
<tr class="odd">
<td align="center">MUPCDH</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens mucin-like protocadherin (MUPCDH), transcript variant 1, mRNA.</td>
<td align="center">0.02058</td>
</tr>
<tr class="even">
<td align="center">CD36</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens CD36 molecule (thrombospondin receptor) (CD36), transcript variant 3, mRNA.</td>
<td align="center">0.02058</td>
</tr>
<tr class="odd">
<td align="center">ENPP7</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens ectonucleotide pyrophosphatase/phosphodiesterase 7 (ENPP7), mRNA.</td>
<td align="center">0.02159</td>
</tr>
<tr class="even">
<td align="center">ABHD5</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens abhydrolase domain containing 5 (ABHD5), mRNA.</td>
<td align="center">0.02206</td>
</tr>
<tr class="odd">
<td align="center">EDN3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens endothelin 3 (EDN3), transcript variant 3, mRNA.</td>
<td align="center">0.02283</td>
</tr>
<tr class="even">
<td align="center">LOC653381</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens similar to Sorbitol dehydrogenase (L-iditol 2-dehydrogenase) (LOC653381), mRNA.</td>
<td align="center">0.02283</td>
</tr>
<tr class="odd">
<td align="center">SORD</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens sorbitol dehydrogenase (SORD), mRNA.</td>
<td align="center">0.0244</td>
</tr>
<tr class="even">
<td align="center">BTNL8</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens butyrophilin-like 8 (BTNL8), transcript variant 1, mRNA.</td>
<td align="center">0.03037</td>
</tr>
<tr class="odd">
<td align="center">SEPP1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens selenoprotein P, plasma, 1 (SEPP1), transcript variant 1, mRNA.</td>
<td align="center">0.03037</td>
</tr>
<tr class="even">
<td align="center">AQP7P2</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens aquaporin 7 pseudogene 2 (AQP7P2), non-coding RNA.</td>
<td align="center">0.03037</td>
</tr>
<tr class="odd">
<td align="center">SHBG</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens sex hormone-binding globulin (SHBG), mRNA.</td>
<td align="center">0.03037</td>
</tr>
<tr class="even">
<td align="center">PCK1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens phosphoenolpyruvate carboxykinase 1 (soluble) (PCK1), mRNA.</td>
<td align="center">0.03037</td>
</tr>
<tr class="odd">
<td align="center">MST1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens macrophage stimulating 1 (hepatocyte growth factor-like) (MST1), mRNA.</td>
<td align="center">0.03037</td>
</tr>
<tr class="even">
<td align="center">RIOK3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens RIO kinase 3 (yeast) (RIOK3), mRNA.</td>
<td align="center">0.03037</td>
</tr>
<tr class="odd">
<td align="center">LCT</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens lactase (LCT), mRNA.</td>
<td align="center">0.03037</td>
</tr>
<tr class="even">
<td align="center">HIST2H2BE</td>
<td align="center">UP</td>
<td align="center">Homo sapiens histone cluster 2, H2be (HIST2H2BE), mRNA.</td>
<td align="center">0.03037</td>
</tr>
<tr class="odd">
<td align="center">GOLPH4</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens golgi phosphoprotein 4 (GOLPH4), mRNA.</td>
<td align="center">0.03037</td>
</tr>
<tr class="even">
<td align="center">ENPP7</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens ectonucleotide pyrophosphatase/phosphodiesterase 7 (ENPP7), mRNA.</td>
<td align="center">0.03085</td>
</tr>
<tr class="odd">
<td align="center">SCG5</td>
<td align="center">UP</td>
<td align="center">Homo sapiens secretogranin V (7B2 protein) (SCG5), mRNA.</td>
<td align="center">0.03105</td>
</tr>
<tr class="even">
<td align="center">LAMA3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens laminin, alpha 3 (LAMA3), transcript variant 1, mRNA.</td>
<td align="center">0.03105</td>
</tr>
<tr class="odd">
<td align="center">ASAH2</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens N-acylsphingosine amidohydrolase (non-lysosomal ceramidase) 2 (ASAH2), mRNA.</td>
<td align="center">0.03105</td>
</tr>
<tr class="even">
<td align="center">AQP11</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens aquaporin 11 (AQP11), mRNA.</td>
<td align="center">0.03164</td>
</tr>
<tr class="odd">
<td align="center">PROM2</td>
<td align="center">UP</td>
<td align="center">Homo sapiens prominin 2 (PROM2), mRNA.</td>
<td align="center">0.03164</td>
</tr>
<tr class="even">
<td align="center">AKR7A3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens aldo-keto reductase family 7, member A3 (aflatoxin aldehyde reductase) (AKR7A3), mRNA.</td>
<td align="center">0.03348</td>
</tr>
<tr class="odd">
<td align="center">TM4SF20</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens transmembrane 4 L six family member 20 (TM4SF20), mRNA.</td>
<td align="center">0.03405</td>
</tr>
<tr class="even">
<td align="center">BEND7</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens BEN domain containing 7 (BEND7), transcript variant 2, mRNA.</td>
<td align="center">0.03405</td>
</tr>
<tr class="odd">
<td align="center">ASAH2</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens N-acylsphingosine amidohydrolase (non-lysosomal ceramidase) 2 (ASAH2), mRNA.</td>
<td align="center">0.03421</td>
</tr>
<tr class="even">
<td align="center">SPDEF</td>
<td align="center">UP</td>
<td align="center">Homo sapiens SAM pointed domain containing ets transcription factor (SPDEF), mRNA.</td>
<td align="center">0.03421</td>
</tr>
<tr class="odd">
<td align="center">CEACAM1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens carcinoembryonic antigen-related cell adhesion molecule 1 (biliary glycoprotein) (CEACAM1), transcript variant 1, mRNA.</td>
<td align="center">0.03431</td>
</tr>
<tr class="even">
<td align="center">LOC653308</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens similar to N-acylsphingosine amidohydrolase 2, transcript variant 1 (LOC653308), mRNA.</td>
<td align="center">0.03431</td>
</tr>
<tr class="odd">
<td align="center">RIOK3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens RIO kinase 3 (yeast) (RIOK3), transcript variant 1, mRNA.</td>
<td align="center">0.03431</td>
</tr>
<tr class="even">
<td align="center">CHN2</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens chimerin (chimaerin) 2 (CHN2), transcript variant 2, mRNA.</td>
<td align="center">0.03431</td>
</tr>
<tr class="odd">
<td align="center">CD36</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens CD36 molecule (thrombospondin receptor) (CD36), transcript variant 1, mRNA.</td>
<td align="center">0.03431</td>
</tr>
<tr class="even">
<td align="center">HLA-DRA</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens major histocompatibility complex, class II, DR alpha (HLA-DRA), mRNA.</td>
<td align="center">0.03431</td>
</tr>
<tr class="odd">
<td align="center">SLC2A12</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens solute carrier family 2 (facilitated glucose transporter), member 12 (SLC2A12), mRNA.</td>
<td align="center">0.03431</td>
</tr>
<tr class="even">
<td align="center">HNF4G</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens hepatocyte nuclear factor 4, gamma (HNF4G), mRNA.</td>
<td align="center">0.03431</td>
</tr>
<tr class="odd">
<td align="center">SORD</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens sorbitol dehydrogenase (SORD), mRNA.</td>
<td align="center">0.0348</td>
</tr>
<tr class="even">
<td align="center">SORD</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens sorbitol dehydrogenase (SORD), mRNA.</td>
<td align="center">0.03619</td>
</tr>
<tr class="odd">
<td align="center">SLC23A1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens solute carrier family 23 (nucleobase transporters), member 1 (SLC23A1), transcript variant 1, mRNA.</td>
<td align="center">0.03619</td>
</tr>
<tr class="even">
<td align="center">SLC46A1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens solute carrier family 46 (folate transporter), member 1 (SLC46A1), mRNA.</td>
<td align="center">0.03619</td>
</tr>
<tr class="odd">
<td align="center">HLA-DRB6</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens major histocompatibility complex, class II, DR beta 6 (pseudogene) (HLA-DRB6), non-coding RNA.</td>
<td align="center">0.03695</td>
</tr>
<tr class="even">
<td align="center">IL32</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens interleukin 32 (IL32), transcript variant 7, mRNA.</td>
<td align="center">0.03736</td>
</tr>
<tr class="odd">
<td align="center">LAMB3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens laminin, beta 3 (LAMB3), transcript variant 1, mRNA.</td>
<td align="center">0.038</td>
</tr>
<tr class="even">
<td align="center">C12ORF35</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens chromosome 12 open reading frame 35 (C12orf35), mRNA.</td>
<td align="center">0.038</td>
</tr>
<tr class="odd">
<td align="center">CPA2</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens carboxypeptidase A2 (pancreatic) (CPA2), mRNA.</td>
<td align="center">0.03936</td>
</tr>
<tr class="even">
<td align="center">FLJ22675</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens hypothetical gene supported by AK026328 (FLJ22675), mRNA.</td>
<td align="center">0.04012</td>
</tr>
<tr class="odd">
<td align="center">LY6E</td>
<td align="center">UP</td>
<td align="center">Homo sapiens lymphocyte antigen 6 complex, locus E (LY6E), mRNA.</td>
<td align="center">0.04012</td>
</tr>
<tr class="even">
<td align="center">IFI27L1</td>
<td align="center">UP</td>
<td align="center">Homo sapiens interferon, alpha-inducible protein 27-like 1 (IFI27L1), transcript variant 1, mRNA.</td>
<td align="center">0.04012</td>
</tr>
<tr class="odd">
<td align="center">HSH2D</td>
<td align="center">UP</td>
<td align="center">Homo sapiens hematopoietic SH2 domain containing (HSH2D), mRNA.</td>
<td align="center">0.04012</td>
</tr>
<tr class="even">
<td align="center">EDN3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens endothelin 3 (EDN3), transcript variant 2, mRNA.</td>
<td align="center">0.04101</td>
</tr>
<tr class="odd">
<td align="center">PLA2G4C</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens phospholipase A2, group IVC (cytosolic, calcium-independent) (PLA2G4C), mRNA.</td>
<td align="center">0.04199</td>
</tr>
<tr class="even">
<td align="center">C8G</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens complement component 8, gamma polypeptide (C8G), mRNA.</td>
<td align="center">0.04242</td>
</tr>
<tr class="odd">
<td align="center">FOXQ1</td>
<td align="center">UP</td>
<td align="center">Homo sapiens forkhead box Q1 (FOXQ1), mRNA.</td>
<td align="center">0.04242</td>
</tr>
<tr class="even">
<td align="center">HMOX1</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens heme oxygenase (decycling) 1 (HMOX1), mRNA.</td>
<td align="center">0.04242</td>
</tr>
<tr class="odd">
<td align="center">ENPP3</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens ectonucleotide pyrophosphatase/phosphodiesterase 3 (ENPP3), mRNA.</td>
<td align="center">0.04286</td>
</tr>
<tr class="even">
<td align="center">LOC100133583</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens similar to major histocompatibility complex, class II, DQ beta 1, transcript variant 2 (LOC100133583), mRNA.</td>
<td align="center">0.04386</td>
</tr>
<tr class="odd">
<td align="center">SUSD2</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens sushi domain containing 2 (SUSD2), mRNA.</td>
<td align="center">0.04386</td>
</tr>
<tr class="even">
<td align="center">OBFC2A</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens oligonucleotide/oligosaccharide-binding fold containing 2A (OBFC2A), mRNA.</td>
<td align="center">0.04388</td>
</tr>
<tr class="odd">
<td align="center">ASAH2</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens N-acylsphingosine amidohydrolase (non-lysosomal ceramidase) 2 (ASAH2), mRNA.</td>
<td align="center">0.04388</td>
</tr>
<tr class="even">
<td align="center">SLC7A7</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens solute carrier family 7 (cationic amino acid transporter, y+ system), member 7 (SLC7A7), mRNA.</td>
<td align="center">0.04433</td>
</tr>
<tr class="odd">
<td align="center">IGFBP2</td>
<td align="center">UP</td>
<td align="center">Homo sapiens insulin-like growth factor binding protein 2, 36kDa (IGFBP2), mRNA.</td>
<td align="center">0.04433</td>
</tr>
<tr class="even">
<td align="center">GUCA2B</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens guanylate cyclase activator 2B (uroguanylin) (GUCA2B), mRNA.</td>
<td align="center">0.04677</td>
</tr>
<tr class="odd">
<td align="center">LOC642073</td>
<td align="center">DOWN</td>
<td align="center">PREDICTED: Homo sapiens similar to MHC class II antigen (LOC642073), mRNA.</td>
<td align="center">0.04682</td>
</tr>
<tr class="even">
<td align="center">IL32</td>
<td align="center">DOWN</td>
<td align="center">Homo sapiens interleukin 32 (IL32), transcript variant 4, mRNA.</td>
<td align="center">0.04688</td>
</tr>
<tr class="odd">
<td align="center">IGFBP5</td>
<td align="center">UP</td>
<td align="center">Homo sapiens insulin-like growth factor binding protein 5 (IGFBP5), mRNA.</td>
<td align="center">0.04706</td>
</tr>
</tbody>
</table>

CAMERA testing
--------------

From the CAMERA documentation:

"camera performs a competitive test in the sense defined by Goeman and Buhlmann (2007). It tests whether the genes in the set are highly ranked in terms of differential expression relative to genes not in the set."

### Hallmark gene sets: top 10 results

#### Duodenal sample results

<table style="width:81%;">
<colgroup>
<col width="36%" />
<col width="16%" />
<col width="13%" />
<col width="13%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">Gene_Set</th>
<th align="center">Direction</th>
<th align="center">FDR</th>
<th align="center">NGenes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">interferon alpha response</td>
<td align="center">Up</td>
<td align="center">1.432e-10</td>
<td align="center">118</td>
</tr>
<tr class="even">
<td align="center">e2f targets</td>
<td align="center">Up</td>
<td align="center">1.495e-09</td>
<td align="center">269</td>
</tr>
<tr class="odd">
<td align="center">g2m checkpoint</td>
<td align="center">Up</td>
<td align="center">2.482e-07</td>
<td align="center">251</td>
</tr>
<tr class="even">
<td align="center">bile acid metabolism</td>
<td align="center">Down</td>
<td align="center">0.0003259</td>
<td align="center">125</td>
</tr>
<tr class="odd">
<td align="center">myc targets v1</td>
<td align="center">Up</td>
<td align="center">0.0007642</td>
<td align="center">287</td>
</tr>
<tr class="even">
<td align="center">myc targets v2</td>
<td align="center">Up</td>
<td align="center">0.002901</td>
<td align="center">79</td>
</tr>
<tr class="odd">
<td align="center">interferon gamma response</td>
<td align="center">Up</td>
<td align="center">0.003457</td>
<td align="center">241</td>
</tr>
<tr class="even">
<td align="center">xenobiotic metabolism</td>
<td align="center">Down</td>
<td align="center">0.006079</td>
<td align="center">219</td>
</tr>
<tr class="odd">
<td align="center">unfolded protein response</td>
<td align="center">Up</td>
<td align="center">0.006459</td>
<td align="center">143</td>
</tr>
<tr class="even">
<td align="center">hypoxia</td>
<td align="center">Down</td>
<td align="center">0.02173</td>
<td align="center">235</td>
</tr>
</tbody>
</table>

#### Rectal sample results

<table style="width:81%;">
<colgroup>
<col width="36%" />
<col width="16%" />
<col width="13%" />
<col width="13%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">Gene_Set</th>
<th align="center">Direction</th>
<th align="center">FDR</th>
<th align="center">NGenes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">myc targets v2</td>
<td align="center">Up</td>
<td align="center">1.887e-07</td>
<td align="center">79</td>
</tr>
<tr class="even">
<td align="center">oxidative phosphorylation</td>
<td align="center">Up</td>
<td align="center">8.293e-05</td>
<td align="center">266</td>
</tr>
<tr class="odd">
<td align="center">allograft rejection</td>
<td align="center">Down</td>
<td align="center">0.00145</td>
<td align="center">232</td>
</tr>
<tr class="even">
<td align="center">cholesterol homeostasis</td>
<td align="center">Up</td>
<td align="center">0.002958</td>
<td align="center">92</td>
</tr>
<tr class="odd">
<td align="center">myc targets v1</td>
<td align="center">Up</td>
<td align="center">0.004697</td>
<td align="center">288</td>
</tr>
<tr class="even">
<td align="center">estrogen response late</td>
<td align="center">Up</td>
<td align="center">0.0103</td>
<td align="center">234</td>
</tr>
<tr class="odd">
<td align="center">uv response up</td>
<td align="center">Up</td>
<td align="center">0.01245</td>
<td align="center">175</td>
</tr>
<tr class="even">
<td align="center">pancreas beta cells</td>
<td align="center">Up</td>
<td align="center">0.01245</td>
<td align="center">29</td>
</tr>
<tr class="odd">
<td align="center">e2f targets</td>
<td align="center">Up</td>
<td align="center">0.02967</td>
<td align="center">262</td>
</tr>
<tr class="even">
<td align="center">unfolded protein response</td>
<td align="center">Up</td>
<td align="center">0.02967</td>
<td align="center">144</td>
</tr>
</tbody>
</table>

#### PBMC sample results

<table style="width:81%;">
<colgroup>
<col width="36%" />
<col width="16%" />
<col width="13%" />
<col width="13%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">Gene_Set</th>
<th align="center">Direction</th>
<th align="center">FDR</th>
<th align="center">NGenes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">tnfa signaling via nfkb</td>
<td align="center">Down</td>
<td align="center">8.921e-09</td>
<td align="center">218</td>
</tr>
<tr class="even">
<td align="center">interferon gamma response</td>
<td align="center">Down</td>
<td align="center">0.006626</td>
<td align="center">250</td>
</tr>
<tr class="odd">
<td align="center">apoptosis</td>
<td align="center">Down</td>
<td align="center">0.0113</td>
<td align="center">204</td>
</tr>
<tr class="even">
<td align="center">complement</td>
<td align="center">Down</td>
<td align="center">0.0136</td>
<td align="center">211</td>
</tr>
<tr class="odd">
<td align="center">mtorc1 signaling</td>
<td align="center">Down</td>
<td align="center">0.02192</td>
<td align="center">260</td>
</tr>
<tr class="even">
<td align="center">hypoxia</td>
<td align="center">Down</td>
<td align="center">0.02603</td>
<td align="center">201</td>
</tr>
<tr class="odd">
<td align="center">estrogen response late</td>
<td align="center">Down</td>
<td align="center">0.02715</td>
<td align="center">168</td>
</tr>
<tr class="even">
<td align="center">myc targets v2</td>
<td align="center">Up</td>
<td align="center">0.03343</td>
<td align="center">76</td>
</tr>
<tr class="odd">
<td align="center">inflammatory response</td>
<td align="center">Down</td>
<td align="center">0.04017</td>
<td align="center">198</td>
</tr>
<tr class="even">
<td align="center">cholesterol homeostasis</td>
<td align="center">Down</td>
<td align="center">0.0726</td>
<td align="center">78</td>
</tr>
</tbody>
</table>

#### PAXgene sample results

<table style="width:81%;">
<colgroup>
<col width="36%" />
<col width="16%" />
<col width="13%" />
<col width="13%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">Gene_Set</th>
<th align="center">Direction</th>
<th align="center">FDR</th>
<th align="center">NGenes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">interferon alpha response</td>
<td align="center">Down</td>
<td align="center">0.0002159</td>
<td align="center">118</td>
</tr>
<tr class="even">
<td align="center">interferon gamma response</td>
<td align="center">Down</td>
<td align="center">0.01146</td>
<td align="center">237</td>
</tr>
<tr class="odd">
<td align="center">tgf beta signaling</td>
<td align="center">Down</td>
<td align="center">0.2055</td>
<td align="center">53</td>
</tr>
<tr class="even">
<td align="center">myc targets v2</td>
<td align="center">Up</td>
<td align="center">0.2055</td>
<td align="center">73</td>
</tr>
<tr class="odd">
<td align="center">mitotic spindle</td>
<td align="center">Up</td>
<td align="center">0.4815</td>
<td align="center">179</td>
</tr>
<tr class="even">
<td align="center">apical surface</td>
<td align="center">Up</td>
<td align="center">0.4815</td>
<td align="center">35</td>
</tr>
<tr class="odd">
<td align="center">hedgehog signaling</td>
<td align="center">Up</td>
<td align="center">0.5361</td>
<td align="center">21</td>
</tr>
<tr class="even">
<td align="center">bile acid metabolism</td>
<td align="center">Up</td>
<td align="center">0.5361</td>
<td align="center">85</td>
</tr>
<tr class="odd">
<td align="center">dna repair</td>
<td align="center">Up</td>
<td align="center">0.5361</td>
<td align="center">175</td>
</tr>
<tr class="even">
<td align="center">apical junction</td>
<td align="center">Up</td>
<td align="center">0.5525</td>
<td align="center">155</td>
</tr>
</tbody>
</table>

### GO biological process gene sets: top 10 results

Sean wrote some code (<https://github.com/seaaan/Bioinformatics/tree/master/GOTermMappingsForCamera>) to extract just the Biological Process gene sets out of all the GO gene sets.

#### Duodenal sample results

<table style="width:88%;">
<colgroup>
<col width="43%" />
<col width="16%" />
<col width="13%" />
<col width="13%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">Gene_Set</th>
<th align="center">Direction</th>
<th align="center">FDR</th>
<th align="center">NGenes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">go flavonoid metabolic process</td>
<td align="center">Down</td>
<td align="center">6.613e-07</td>
<td align="center">30</td>
</tr>
<tr class="even">
<td align="center">go neutral lipid biosynthetic process</td>
<td align="center">Down</td>
<td align="center">1.934e-06</td>
<td align="center">34</td>
</tr>
<tr class="odd">
<td align="center">go acylglycerol biosynthetic process</td>
<td align="center">Down</td>
<td align="center">1.934e-06</td>
<td align="center">34</td>
</tr>
<tr class="even">
<td align="center">go dna replication</td>
<td align="center">Up</td>
<td align="center">3.922e-05</td>
<td align="center">237</td>
</tr>
<tr class="odd">
<td align="center">go glucuronate metabolic process</td>
<td align="center">Down</td>
<td align="center">3.922e-05</td>
<td align="center">26</td>
</tr>
<tr class="even">
<td align="center">go uronic acid metabolic process</td>
<td align="center">Down</td>
<td align="center">3.922e-05</td>
<td align="center">26</td>
</tr>
<tr class="odd">
<td align="center">go response to type i interferon</td>
<td align="center">Up</td>
<td align="center">3.922e-05</td>
<td align="center">78</td>
</tr>
<tr class="even">
<td align="center">go response to interferon alpha</td>
<td align="center">Up</td>
<td align="center">6.198e-05</td>
<td align="center">28</td>
</tr>
<tr class="odd">
<td align="center">go dna replication initiation</td>
<td align="center">Up</td>
<td align="center">7.884e-05</td>
<td align="center">29</td>
</tr>
<tr class="even">
<td align="center">go response to xenobiotic stimulus</td>
<td align="center">Down</td>
<td align="center">9.868e-05</td>
<td align="center">102</td>
</tr>
</tbody>
</table>

#### Rectal sample results

<table style="width:85%;">
<colgroup>
<col width="43%" />
<col width="16%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">Gene_Set</th>
<th align="center">Direction</th>
<th align="center">FDR</th>
<th align="center">NGenes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">go hemidesmosome assembly</td>
<td align="center">Up</td>
<td align="center">0.002715</td>
<td align="center">16</td>
</tr>
<tr class="even">
<td align="center">go oxidative phosphorylation</td>
<td align="center">Up</td>
<td align="center">0.03887</td>
<td align="center">89</td>
</tr>
<tr class="odd">
<td align="center">go ire1 mediated unfolded protein response</td>
<td align="center">Up</td>
<td align="center">0.04367</td>
<td align="center">77</td>
</tr>
<tr class="even">
<td align="center">go electron transport chain</td>
<td align="center">Up</td>
<td align="center">0.04367</td>
<td align="center">102</td>
</tr>
<tr class="odd">
<td align="center">go regulation of cell projection size</td>
<td align="center">Up</td>
<td align="center">0.04367</td>
<td align="center">13</td>
</tr>
<tr class="even">
<td align="center">go positive regulation of protein localization to cell periphery</td>
<td align="center">Up</td>
<td align="center">0.04367</td>
<td align="center">52</td>
</tr>
<tr class="odd">
<td align="center">go positive regulation of protein localization to plasma membrane</td>
<td align="center">Up</td>
<td align="center">0.04367</td>
<td align="center">52</td>
</tr>
<tr class="even">
<td align="center">go cellular respiration</td>
<td align="center">Up</td>
<td align="center">0.04367</td>
<td align="center">156</td>
</tr>
<tr class="odd">
<td align="center">go energy homeostasis</td>
<td align="center">Down</td>
<td align="center">0.04367</td>
<td align="center">15</td>
</tr>
<tr class="even">
<td align="center">go negative regulation of endoplasmic reticulum stress induced intrinsic apoptotic signaling pathway</td>
<td align="center">Up</td>
<td align="center">0.04367</td>
<td align="center">22</td>
</tr>
</tbody>
</table>

#### PBMC sample results

<table style="width:81%;">
<colgroup>
<col width="41%" />
<col width="16%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">Gene_Set</th>
<th align="center">Direction</th>
<th align="center">FDR</th>
<th align="center">NGenes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">go regulation of secondary metabolic process</td>
<td align="center">Down</td>
<td align="center">0.01013</td>
<td align="center">9</td>
</tr>
<tr class="even">
<td align="center">go granulocyte migration</td>
<td align="center">Down</td>
<td align="center">0.01013</td>
<td align="center">51</td>
</tr>
<tr class="odd">
<td align="center">go positive regulation of transcription from rna polymerase ii promoter in response to stress</td>
<td align="center">Down</td>
<td align="center">0.01013</td>
<td align="center">28</td>
</tr>
<tr class="even">
<td align="center">go lymph node development</td>
<td align="center">Up</td>
<td align="center">0.01013</td>
<td align="center">15</td>
</tr>
<tr class="odd">
<td align="center">go monocyte chemotaxis</td>
<td align="center">Down</td>
<td align="center">0.02234</td>
<td align="center">23</td>
</tr>
<tr class="even">
<td align="center">go response to interferon gamma</td>
<td align="center">Down</td>
<td align="center">0.04605</td>
<td align="center">139</td>
</tr>
<tr class="odd">
<td align="center">go cellular response to interferon gamma</td>
<td align="center">Down</td>
<td align="center">0.04605</td>
<td align="center">117</td>
</tr>
<tr class="even">
<td align="center">go positive regulation of vascular endothelial growth factor production</td>
<td align="center">Down</td>
<td align="center">0.04605</td>
<td align="center">28</td>
</tr>
<tr class="odd">
<td align="center">go negative regulation of viral genome replication</td>
<td align="center">Down</td>
<td align="center">0.05122</td>
<td align="center">60</td>
</tr>
<tr class="even">
<td align="center">go epithelial cell maturation</td>
<td align="center">Down</td>
<td align="center">0.05122</td>
<td align="center">14</td>
</tr>
</tbody>
</table>

#### PAXgene sample results

<table style="width:79%;">
<colgroup>
<col width="40%" />
<col width="16%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">Gene_Set</th>
<th align="center">Direction</th>
<th align="center">FDR</th>
<th align="center">NGenes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">go regulation of secondary metabolic process</td>
<td align="center">Down</td>
<td align="center">0.01588</td>
<td align="center">9</td>
</tr>
<tr class="even">
<td align="center">go negative regulation of viral genome replication</td>
<td align="center">Down</td>
<td align="center">0.1076</td>
<td align="center">61</td>
</tr>
<tr class="odd">
<td align="center">go response to type i interferon</td>
<td align="center">Down</td>
<td align="center">0.1213</td>
<td align="center">78</td>
</tr>
<tr class="even">
<td align="center">go cellular defense response</td>
<td align="center">Down</td>
<td align="center">0.1994</td>
<td align="center">53</td>
</tr>
<tr class="odd">
<td align="center">go interferon gamma mediated signaling pathway</td>
<td align="center">Down</td>
<td align="center">0.222</td>
<td align="center">82</td>
</tr>
<tr class="even">
<td align="center">go cellular response to interferon gamma</td>
<td align="center">Down</td>
<td align="center">0.222</td>
<td align="center">112</td>
</tr>
<tr class="odd">
<td align="center">go ganglion development</td>
<td align="center">Down</td>
<td align="center">0.3379</td>
<td align="center">3</td>
</tr>
<tr class="even">
<td align="center">go respiratory burst</td>
<td align="center">Down</td>
<td align="center">0.3575</td>
<td align="center">15</td>
</tr>
<tr class="odd">
<td align="center">go response to interferon gamma</td>
<td align="center">Down</td>
<td align="center">0.3575</td>
<td align="center">132</td>
</tr>
<tr class="even">
<td align="center">go cellular response to vitamin d</td>
<td align="center">Down</td>
<td align="center">0.5703</td>
<td align="center">12</td>
</tr>
</tbody>
</table>

### MTN-007 gene sets

Here I am comparing the probes in this experiment to significantly differentially expressed probes from MTN-007 9cm biopsies at 7 days.

<table style="width:75%;">
<colgroup>
<col width="18%" />
<col width="12%" />
<col width="16%" />
<col width="13%" />
<col width="13%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">Gene_Sets</th>
<th align="center">Tissue</th>
<th align="center">Direction</th>
<th align="center">FDR</th>
<th align="center">NGenes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">MTN_007 Down</td>
<td align="center">Duodenal</td>
<td align="center">Down</td>
<td align="center">1.333e-05</td>
<td align="center">765</td>
</tr>
<tr class="even">
<td align="center">MTN_007 Up</td>
<td align="center">Duodenal</td>
<td align="center">Up</td>
<td align="center">0.008987</td>
<td align="center">181</td>
</tr>
<tr class="odd">
<td align="center">MTN_007 Down</td>
<td align="center">Rectal</td>
<td align="center">Down</td>
<td align="center">1.424e-05</td>
<td align="center">787</td>
</tr>
<tr class="even">
<td align="center">MTN_007 Up</td>
<td align="center">Rectal</td>
<td align="center">Down</td>
<td align="center">0.004617</td>
<td align="center">191</td>
</tr>
<tr class="odd">
<td align="center">MTN_007 Down</td>
<td align="center">PBMC</td>
<td align="center">Down</td>
<td align="center">0.369</td>
<td align="center">735</td>
</tr>
<tr class="even">
<td align="center">MTN_007 Up</td>
<td align="center">PBMC</td>
<td align="center">Down</td>
<td align="center">0.369</td>
<td align="center">152</td>
</tr>
<tr class="odd">
<td align="center">MTN_007 Down</td>
<td align="center">PAXgene</td>
<td align="center">Down</td>
<td align="center">0.08041</td>
<td align="center">675</td>
</tr>
<tr class="even">
<td align="center">MTN_007 Up</td>
<td align="center">PAXgene</td>
<td align="center">Up</td>
<td align="center">0.7308</td>
<td align="center">144</td>
</tr>
</tbody>
</table>

Which DE probes from the PreP study overlap with those from MTN-007?
--------------------------------------------------------------------

<table style="width:86%;">
<colgroup>
<col width="19%" />
<col width="15%" />
<col width="41%" />
<col width="9%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">TargetID</th>
<th align="center">DEFINITION</th>
<th align="center">logFC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>3850328</strong></td>
<td align="center">MUPCDH</td>
<td align="center">Homo sapiens mucin-like protocadherin (MUPCDH), transcript variant 1, mRNA.</td>
<td align="center">-0.5277</td>
</tr>
<tr class="even">
<td align="center"><strong>670333</strong></td>
<td align="center">EDN3</td>
<td align="center">Homo sapiens endothelin 3 (EDN3), transcript variant 3, mRNA.</td>
<td align="center">-0.6583</td>
</tr>
<tr class="odd">
<td align="center"><strong>5870221</strong></td>
<td align="center">GOLPH4</td>
<td align="center">Homo sapiens golgi phosphoprotein 4 (GOLPH4), mRNA.</td>
<td align="center">-0.5256</td>
</tr>
<tr class="even">
<td align="center"><strong>1410240</strong></td>
<td align="center">EDN3</td>
<td align="center">Homo sapiens endothelin 3 (EDN3), transcript variant 2, mRNA.</td>
<td align="center">-0.5274</td>
</tr>
</tbody>
</table>

CAMERA test of Hallmark interferon alpha geneset founder sets
-------------------------------------------------------------

#### Duodenal sample results

<table style="width:88%;">
<colgroup>
<col width="43%" />
<col width="16%" />
<col width="13%" />
<col width="13%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">Gene_Set</th>
<th align="center">Direction</th>
<th align="center">FDR</th>
<th align="center">NGenes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">moserle ifna response</td>
<td align="center">Up</td>
<td align="center">4.674e-12</td>
<td align="center">40</td>
</tr>
<tr class="even">
<td align="center">bennett systemic lupus erythematosus</td>
<td align="center">Up</td>
<td align="center">4.674e-12</td>
<td align="center">36</td>
</tr>
<tr class="odd">
<td align="center">einav interferon signature in cancer</td>
<td align="center">Up</td>
<td align="center">2.082e-10</td>
<td align="center">42</td>
</tr>
<tr class="even">
<td align="center">zhang interferon response</td>
<td align="center">Up</td>
<td align="center">6.545e-10</td>
<td align="center">31</td>
</tr>
<tr class="odd">
<td align="center">dauer stat3 targets dn</td>
<td align="center">Up</td>
<td align="center">1.478e-09</td>
<td align="center">64</td>
</tr>
<tr class="even">
<td align="center">hecker ifnb1 targets</td>
<td align="center">Up</td>
<td align="center">2.447e-09</td>
<td align="center">104</td>
</tr>
<tr class="odd">
<td align="center">browne interferon responsive genes</td>
<td align="center">Up</td>
<td align="center">3.261e-09</td>
<td align="center">99</td>
</tr>
<tr class="even">
<td align="center">urosevic response to imiquimod</td>
<td align="center">Up</td>
<td align="center">2.097e-08</td>
<td align="center">33</td>
</tr>
<tr class="odd">
<td align="center">radaeva response to ifna1 up</td>
<td align="center">Up</td>
<td align="center">4.137e-08</td>
<td align="center">69</td>
</tr>
<tr class="even">
<td align="center">stambolsky targets of mutated tp53 dn</td>
<td align="center">Up</td>
<td align="center">1.124e-07</td>
<td align="center">56</td>
</tr>
</tbody>
</table>

#### Rectal sample results

<table style="width:85%;">
<colgroup>
<col width="43%" />
<col width="16%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">Gene_Set</th>
<th align="center">Direction</th>
<th align="center">FDR</th>
<th align="center">NGenes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">honma docetaxel resistance</td>
<td align="center">Up</td>
<td align="center">0.005468</td>
<td align="center">43</td>
</tr>
<tr class="even">
<td align="center">module 119</td>
<td align="center">Down</td>
<td align="center">0.005468</td>
<td align="center">172</td>
</tr>
<tr class="odd">
<td align="center">module 171</td>
<td align="center">Down</td>
<td align="center">0.01158</td>
<td align="center">151</td>
</tr>
<tr class="even">
<td align="center">module 436</td>
<td align="center">Down</td>
<td align="center">0.01158</td>
<td align="center">141</td>
</tr>
<tr class="odd">
<td align="center">module 292</td>
<td align="center">Down</td>
<td align="center">0.01158</td>
<td align="center">144</td>
</tr>
<tr class="even">
<td align="center">module 345</td>
<td align="center">Down</td>
<td align="center">0.01158</td>
<td align="center">134</td>
</tr>
<tr class="odd">
<td align="center">xu hgf targets induced by akt1 6hr</td>
<td align="center">Up</td>
<td align="center">0.01158</td>
<td align="center">24</td>
</tr>
<tr class="even">
<td align="center">module 208</td>
<td align="center">Down</td>
<td align="center">0.01358</td>
<td align="center">132</td>
</tr>
<tr class="odd">
<td align="center">reactome interferon gamma signaling</td>
<td align="center">Down</td>
<td align="center">0.01358</td>
<td align="center">68</td>
</tr>
<tr class="even">
<td align="center">becker tamoxifen resistance up</td>
<td align="center">Up</td>
<td align="center">0.02004</td>
<td align="center">56</td>
</tr>
</tbody>
</table>

#### PBMC sample results

<table style="width:86%;">
<colgroup>
<col width="41%" />
<col width="16%" />
<col width="13%" />
<col width="13%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">Gene_Set</th>
<th align="center">Direction</th>
<th align="center">FDR</th>
<th align="center">NGenes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">liang silenced by methylation 2</td>
<td align="center">Down</td>
<td align="center">7.635e-05</td>
<td align="center">47</td>
</tr>
<tr class="even">
<td align="center">hecker ifnb1 targets</td>
<td align="center">Down</td>
<td align="center">7.635e-05</td>
<td align="center">100</td>
</tr>
<tr class="odd">
<td align="center">seitz neoplastic transformation by 8p deletion up</td>
<td align="center">Down</td>
<td align="center">0.0002599</td>
<td align="center">66</td>
</tr>
<tr class="even">
<td align="center">moserle ifna response</td>
<td align="center">Down</td>
<td align="center">0.001732</td>
<td align="center">39</td>
</tr>
<tr class="odd">
<td align="center">jackson dnmt1 targets up</td>
<td align="center">Down</td>
<td align="center">0.001922</td>
<td align="center">77</td>
</tr>
<tr class="even">
<td align="center">jison sickle cell disease up</td>
<td align="center">Down</td>
<td align="center">0.003179</td>
<td align="center">208</td>
</tr>
<tr class="odd">
<td align="center">roeth tert targets up</td>
<td align="center">Down</td>
<td align="center">0.003262</td>
<td align="center">15</td>
</tr>
<tr class="even">
<td align="center">takeda targets of nup98 hoxa9 fusion 8d up</td>
<td align="center">Down</td>
<td align="center">0.003262</td>
<td align="center">121</td>
</tr>
<tr class="odd">
<td align="center">mel18 dn.v1 dn</td>
<td align="center">Down</td>
<td align="center">0.004138</td>
<td align="center">93</td>
</tr>
<tr class="even">
<td align="center">dauer stat3 targets dn</td>
<td align="center">Down</td>
<td align="center">0.005241</td>
<td align="center">65</td>
</tr>
</tbody>
</table>

#### PAXgene sample results

<table style="width:86%;">
<colgroup>
<col width="41%" />
<col width="16%" />
<col width="13%" />
<col width="13%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">Gene_Set</th>
<th align="center">Direction</th>
<th align="center">FDR</th>
<th align="center">NGenes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">moserle ifna response</td>
<td align="center">Down</td>
<td align="center">0.0002304</td>
<td align="center">40</td>
</tr>
<tr class="even">
<td align="center">einav interferon signature in cancer</td>
<td align="center">Down</td>
<td align="center">0.0002304</td>
<td align="center">43</td>
</tr>
<tr class="odd">
<td align="center">browne interferon responsive genes</td>
<td align="center">Down</td>
<td align="center">0.0002304</td>
<td align="center">92</td>
</tr>
<tr class="even">
<td align="center">bowie response to tamoxifen</td>
<td align="center">Down</td>
<td align="center">0.0002304</td>
<td align="center">29</td>
</tr>
<tr class="odd">
<td align="center">hecker ifnb1 targets</td>
<td align="center">Down</td>
<td align="center">0.0002304</td>
<td align="center">107</td>
</tr>
<tr class="even">
<td align="center">zhang interferon response</td>
<td align="center">Down</td>
<td align="center">0.0002304</td>
<td align="center">32</td>
</tr>
<tr class="odd">
<td align="center">bennett systemic lupus erythematosus</td>
<td align="center">Down</td>
<td align="center">0.0002881</td>
<td align="center">40</td>
</tr>
<tr class="even">
<td align="center">dauer stat3 targets dn</td>
<td align="center">Down</td>
<td align="center">0.0003593</td>
<td align="center">62</td>
</tr>
<tr class="odd">
<td align="center">sana response to ifng up</td>
<td align="center">Down</td>
<td align="center">0.0003593</td>
<td align="center">81</td>
</tr>
<tr class="even">
<td align="center">seitz neoplastic transformation by 8p deletion up</td>
<td align="center">Down</td>
<td align="center">0.000514</td>
<td align="center">62</td>
</tr>
</tbody>
</table>

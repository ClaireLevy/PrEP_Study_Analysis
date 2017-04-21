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

The Duodenal samples were the only ones with any differentially expressed probes. There were 70 downregulated probes and 11 upregulated probes.

Changes in the Duodenum pre vs post-prEP: logFC cutoff = 0.5, p-value cut-off = 0.05
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

<table style="width:99%;">
<colgroup>
<col width="56%" />
<col width="12%" />
<col width="16%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">NGenes</th>
<th align="center">Direction</th>
<th align="center">PValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>HALLMARK_INTERFERON_ALPHA_RESPONSE</strong></td>
<td align="center">118</td>
<td align="center">Up</td>
<td align="center">2.863e-12</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_E2F_TARGETS</strong></td>
<td align="center">269</td>
<td align="center">Up</td>
<td align="center">5.98e-11</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_G2M_CHECKPOINT</strong></td>
<td align="center">251</td>
<td align="center">Up</td>
<td align="center">1.489e-08</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_BILE_ACID_METABOLISM</strong></td>
<td align="center">125</td>
<td align="center">Down</td>
<td align="center">2.607e-05</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_MYC_TARGETS_V1</strong></td>
<td align="center">287</td>
<td align="center">Up</td>
<td align="center">7.642e-05</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_MYC_TARGETS_V2</strong></td>
<td align="center">79</td>
<td align="center">Up</td>
<td align="center">0.0003481</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_INTERFERON_GAMMA_RESPONSE</strong></td>
<td align="center">241</td>
<td align="center">Up</td>
<td align="center">0.0004839</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_XENOBIOTIC_METABOLISM</strong></td>
<td align="center">219</td>
<td align="center">Down</td>
<td align="center">0.0009727</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_UNFOLDED_PROTEIN_RESPONSE</strong></td>
<td align="center">143</td>
<td align="center">Up</td>
<td align="center">0.001163</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_HYPOXIA</strong></td>
<td align="center">235</td>
<td align="center">Down</td>
<td align="center">0.004346</td>
</tr>
</tbody>
</table>

#### Rectal sample results

<table style="width:99%;">
<colgroup>
<col width="56%" />
<col width="12%" />
<col width="16%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">NGenes</th>
<th align="center">Direction</th>
<th align="center">PValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>HALLMARK_MYC_TARGETS_V2</strong></td>
<td align="center">79</td>
<td align="center">Up</td>
<td align="center">3.773e-09</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_OXIDATIVE_PHOSPHORYLATION</strong></td>
<td align="center">266</td>
<td align="center">Up</td>
<td align="center">3.317e-06</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_ALLOGRAFT_REJECTION</strong></td>
<td align="center">232</td>
<td align="center">Down</td>
<td align="center">8.701e-05</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_CHOLESTEROL_HOMEOSTASIS</strong></td>
<td align="center">92</td>
<td align="center">Up</td>
<td align="center">0.0002366</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_MYC_TARGETS_V1</strong></td>
<td align="center">288</td>
<td align="center">Up</td>
<td align="center">0.0004697</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_ESTROGEN_RESPONSE_LATE</strong></td>
<td align="center">234</td>
<td align="center">Up</td>
<td align="center">0.001236</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_UV_RESPONSE_UP</strong></td>
<td align="center">175</td>
<td align="center">Up</td>
<td align="center">0.001877</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_PANCREAS_BETA_CELLS</strong></td>
<td align="center">29</td>
<td align="center">Up</td>
<td align="center">0.001992</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_E2F_TARGETS</strong></td>
<td align="center">262</td>
<td align="center">Up</td>
<td align="center">0.005781</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_UNFOLDED_PROTEIN_RESPONSE</strong></td>
<td align="center">144</td>
<td align="center">Up</td>
<td align="center">0.006305</td>
</tr>
</tbody>
</table>

#### PBMC sample results

<table style="width:99%;">
<colgroup>
<col width="56%" />
<col width="12%" />
<col width="16%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">NGenes</th>
<th align="center">Direction</th>
<th align="center">PValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>HALLMARK_TNFA_SIGNALING_VIA_NFKB</strong></td>
<td align="center">218</td>
<td align="center">Down</td>
<td align="center">1.784e-10</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_INTERFERON_GAMMA_RESPONSE</strong></td>
<td align="center">250</td>
<td align="center">Down</td>
<td align="center">0.000265</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_APOPTOSIS</strong></td>
<td align="center">204</td>
<td align="center">Down</td>
<td align="center">0.0006783</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_COMPLEMENT</strong></td>
<td align="center">211</td>
<td align="center">Down</td>
<td align="center">0.001088</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_MTORC1_SIGNALING</strong></td>
<td align="center">260</td>
<td align="center">Down</td>
<td align="center">0.002192</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_HYPOXIA</strong></td>
<td align="center">201</td>
<td align="center">Down</td>
<td align="center">0.003124</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_ESTROGEN_RESPONSE_LATE</strong></td>
<td align="center">168</td>
<td align="center">Down</td>
<td align="center">0.003801</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_MYC_TARGETS_V2</strong></td>
<td align="center">76</td>
<td align="center">Up</td>
<td align="center">0.005348</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_INFLAMMATORY_RESPONSE</strong></td>
<td align="center">198</td>
<td align="center">Down</td>
<td align="center">0.00723</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_CHOLESTEROL_HOMEOSTASIS</strong></td>
<td align="center">78</td>
<td align="center">Down</td>
<td align="center">0.01452</td>
</tr>
</tbody>
</table>

#### PAXgene sample results

<table style="width:99%;">
<colgroup>
<col width="56%" />
<col width="12%" />
<col width="16%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">NGenes</th>
<th align="center">Direction</th>
<th align="center">PValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>HALLMARK_INTERFERON_ALPHA_RESPONSE</strong></td>
<td align="center">118</td>
<td align="center">Down</td>
<td align="center">4.318e-06</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_INTERFERON_GAMMA_RESPONSE</strong></td>
<td align="center">237</td>
<td align="center">Down</td>
<td align="center">0.0004584</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_TGF_BETA_SIGNALING</strong></td>
<td align="center">53</td>
<td align="center">Down</td>
<td align="center">0.01598</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_MYC_TARGETS_V2</strong></td>
<td align="center">73</td>
<td align="center">Up</td>
<td align="center">0.01644</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_MITOTIC_SPINDLE</strong></td>
<td align="center">179</td>
<td align="center">Up</td>
<td align="center">0.04898</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_APICAL_SURFACE</strong></td>
<td align="center">35</td>
<td align="center">Up</td>
<td align="center">0.05778</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_HEDGEHOG_SIGNALING</strong></td>
<td align="center">21</td>
<td align="center">Up</td>
<td align="center">0.09036</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_BILE_ACID_METABOLISM</strong></td>
<td align="center">85</td>
<td align="center">Up</td>
<td align="center">0.09301</td>
</tr>
<tr class="odd">
<td align="center"><strong>HALLMARK_DNA_REPAIR</strong></td>
<td align="center">175</td>
<td align="center">Up</td>
<td align="center">0.09649</td>
</tr>
<tr class="even">
<td align="center"><strong>HALLMARK_APICAL_JUNCTION</strong></td>
<td align="center">155</td>
<td align="center">Up</td>
<td align="center">0.1105</td>
</tr>
</tbody>
</table>

### GO biological process gene sets: top 10 results

Sean wrote some code (<https://github.com/seaaan/Bioinformatics/tree/master/GOTermMappingsForCamera>) to extract just the Biological Process gene sets out of all the GO gene sets.

#### Duodenal sample Results

<table>
<colgroup>
<col width="59%" />
<col width="12%" />
<col width="16%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">NGenes</th>
<th align="center">Direction</th>
<th align="center">PValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>GO_FLAVONOID_METABOLIC_PROCESS</strong></td>
<td align="center">30</td>
<td align="center">Down</td>
<td align="center">1.426e-10</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_NEUTRAL_LIPID_BIOSYNTHETIC_PROCESS</strong></td>
<td align="center">34</td>
<td align="center">Down</td>
<td align="center">1.252e-09</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_ACYLGLYCEROL_BIOSYNTHETIC_PROCESS</strong></td>
<td align="center">34</td>
<td align="center">Down</td>
<td align="center">1.252e-09</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_DNA_REPLICATION</strong></td>
<td align="center">237</td>
<td align="center">Up</td>
<td align="center">3.555e-08</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_GLUCURONATE_METABOLIC_PROCESS</strong></td>
<td align="center">26</td>
<td align="center">Down</td>
<td align="center">5.542e-08</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_URONIC_ACID_METABOLIC_PROCESS</strong></td>
<td align="center">26</td>
<td align="center">Down</td>
<td align="center">5.542e-08</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_RESPONSE_TO_TYPE_I_INTERFERON</strong></td>
<td align="center">78</td>
<td align="center">Up</td>
<td align="center">5.922e-08</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_RESPONSE_TO_INTERFERON_ALPHA</strong></td>
<td align="center">28</td>
<td align="center">Up</td>
<td align="center">1.07e-07</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_DNA_REPLICATION_INITIATION</strong></td>
<td align="center">29</td>
<td align="center">Up</td>
<td align="center">1.531e-07</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_RESPONSE_TO_XENOBIOTIC_STIMULUS</strong></td>
<td align="center">102</td>
<td align="center">Down</td>
<td align="center">2.128e-07</td>
</tr>
</tbody>
</table>

#### Rectal sample Results

<table>
<caption>Table continues below</caption>
<colgroup>
<col width="93%" />
<col width="6%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">NGenes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>GO_HEMIDESMOSOME_ASSEMBLY</strong></td>
<td align="center">16</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_OXIDATIVE_PHOSPHORYLATION</strong></td>
<td align="center">89</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_IRE1_MEDIATED_UNFOLDED_PROTEIN_RESPONSE</strong></td>
<td align="center">77</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_ELECTRON_TRANSPORT_CHAIN</strong></td>
<td align="center">102</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_REGULATION_OF_CELL_PROJECTION_SIZE</strong></td>
<td align="center">13</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_POSITIVE_REGULATION_OF_PROTEIN_LOCALIZATION_TO_CELL_PERIPHERY</strong></td>
<td align="center">52</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_POSITIVE_REGULATION_OF_PROTEIN_LOCALIZATION_TO_PLASMA_MEMBRANE</strong></td>
<td align="center">52</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_CELLULAR_RESPIRATION</strong></td>
<td align="center">156</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_ENERGY_HOMEOSTASIS</strong></td>
<td align="center">15</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_NEGATIVE_REGULATION_OF_ENDOPLASMIC_RETICULUM_STRESS_INDUCED_INTRINSIC_APOPTOTIC_SIGNALING_PATHWAY</strong></td>
<td align="center">22</td>
</tr>
</tbody>
</table>

<table>
<caption>Table continues below</caption>
<colgroup>
<col width="90%" />
<col width="9%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>GO_HEMIDESMOSOME_ASSEMBLY</strong></td>
<td align="center">Up</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_OXIDATIVE_PHOSPHORYLATION</strong></td>
<td align="center">Up</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_IRE1_MEDIATED_UNFOLDED_PROTEIN_RESPONSE</strong></td>
<td align="center">Up</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_ELECTRON_TRANSPORT_CHAIN</strong></td>
<td align="center">Up</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_REGULATION_OF_CELL_PROJECTION_SIZE</strong></td>
<td align="center">Up</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_POSITIVE_REGULATION_OF_PROTEIN_LOCALIZATION_TO_CELL_PERIPHERY</strong></td>
<td align="center">Up</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_POSITIVE_REGULATION_OF_PROTEIN_LOCALIZATION_TO_PLASMA_MEMBRANE</strong></td>
<td align="center">Up</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_CELLULAR_RESPIRATION</strong></td>
<td align="center">Up</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_ENERGY_HOMEOSTASIS</strong></td>
<td align="center">Down</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_NEGATIVE_REGULATION_OF_ENDOPLASMIC_RETICULUM_STRESS_INDUCED_INTRINSIC_APOPTOTIC_SIGNALING_PATHWAY</strong></td>
<td align="center">Up</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col width="92%" />
<col width="7%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">PValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>GO_HEMIDESMOSOME_ASSEMBLY</strong></td>
<td align="center">5.857e-07</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_OXIDATIVE_PHOSPHORYLATION</strong></td>
<td align="center">1.677e-05</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_IRE1_MEDIATED_UNFOLDED_PROTEIN_RESPONSE</strong></td>
<td align="center">3.829e-05</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_ELECTRON_TRANSPORT_CHAIN</strong></td>
<td align="center">3.923e-05</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_REGULATION_OF_CELL_PROJECTION_SIZE</strong></td>
<td align="center">7.242e-05</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_POSITIVE_REGULATION_OF_PROTEIN_LOCALIZATION_TO_CELL_PERIPHERY</strong></td>
<td align="center">8.031e-05</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_POSITIVE_REGULATION_OF_PROTEIN_LOCALIZATION_TO_PLASMA_MEMBRANE</strong></td>
<td align="center">8.031e-05</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_CELLULAR_RESPIRATION</strong></td>
<td align="center">8.921e-05</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_ENERGY_HOMEOSTASIS</strong></td>
<td align="center">0.0001014</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_NEGATIVE_REGULATION_OF_ENDOPLASMIC_RETICULUM_STRESS_INDUCED_INTRINSIC_APOPTOTIC_SIGNALING_PATHWAY</strong></td>
<td align="center">0.000124</td>
</tr>
</tbody>
</table>

#### PBMC sample results

<table>
<caption>Table continues below</caption>
<colgroup>
<col width="92%" />
<col width="7%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">NGenes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>GO_REGULATION_OF_SECONDARY_METABOLIC_PROCESS</strong></td>
<td align="center">9</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_GRANULOCYTE_MIGRATION</strong></td>
<td align="center">51</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_POSITIVE_REGULATION_OF_TRANSCRIPTION_FROM_RNA_POLYMERASE_II_PROMOTER_IN_RESPONSE_TO_STRESS</strong></td>
<td align="center">28</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_LYMPH_NODE_DEVELOPMENT</strong></td>
<td align="center">15</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_MONOCYTE_CHEMOTAXIS</strong></td>
<td align="center">23</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_RESPONSE_TO_INTERFERON_GAMMA</strong></td>
<td align="center">139</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_CELLULAR_RESPONSE_TO_INTERFERON_GAMMA</strong></td>
<td align="center">117</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_POSITIVE_REGULATION_OF_VASCULAR_ENDOTHELIAL_GROWTH_FACTOR_PRODUCTION</strong></td>
<td align="center">28</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_NEGATIVE_REGULATION_OF_VIRAL_GENOME_REPLICATION</strong></td>
<td align="center">60</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_EPITHELIAL_CELL_MATURATION</strong></td>
<td align="center">14</td>
</tr>
</tbody>
</table>

<table>
<caption>Table continues below</caption>
<colgroup>
<col width="90%" />
<col width="9%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>GO_REGULATION_OF_SECONDARY_METABOLIC_PROCESS</strong></td>
<td align="center">Down</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_GRANULOCYTE_MIGRATION</strong></td>
<td align="center">Down</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_POSITIVE_REGULATION_OF_TRANSCRIPTION_FROM_RNA_POLYMERASE_II_PROMOTER_IN_RESPONSE_TO_STRESS</strong></td>
<td align="center">Down</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_LYMPH_NODE_DEVELOPMENT</strong></td>
<td align="center">Up</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_MONOCYTE_CHEMOTAXIS</strong></td>
<td align="center">Down</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_RESPONSE_TO_INTERFERON_GAMMA</strong></td>
<td align="center">Down</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_CELLULAR_RESPONSE_TO_INTERFERON_GAMMA</strong></td>
<td align="center">Down</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_POSITIVE_REGULATION_OF_VASCULAR_ENDOTHELIAL_GROWTH_FACTOR_PRODUCTION</strong></td>
<td align="center">Down</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_NEGATIVE_REGULATION_OF_VIRAL_GENOME_REPLICATION</strong></td>
<td align="center">Down</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_EPITHELIAL_CELL_MATURATION</strong></td>
<td align="center">Down</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col width="91%" />
<col width="8%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">PValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>GO_REGULATION_OF_SECONDARY_METABOLIC_PROCESS</strong></td>
<td align="center">2.955e-06</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_GRANULOCYTE_MIGRATION</strong></td>
<td align="center">5.253e-06</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_POSITIVE_REGULATION_OF_TRANSCRIPTION_FROM_RNA_POLYMERASE_II_PROMOTER_IN_RESPONSE_TO_STRESS</strong></td>
<td align="center">8.208e-06</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_LYMPH_NODE_DEVELOPMENT</strong></td>
<td align="center">8.738e-06</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_MONOCYTE_CHEMOTAXIS</strong></td>
<td align="center">2.409e-05</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_RESPONSE_TO_INTERFERON_GAMMA</strong></td>
<td align="center">6.079e-05</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_CELLULAR_RESPONSE_TO_INTERFERON_GAMMA</strong></td>
<td align="center">7.178e-05</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_POSITIVE_REGULATION_OF_VASCULAR_ENDOTHELIAL_GROWTH_FACTOR_PRODUCTION</strong></td>
<td align="center">7.947e-05</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_NEGATIVE_REGULATION_OF_VIRAL_GENOME_REPLICATION</strong></td>
<td align="center">0.0001017</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_EPITHELIAL_CELL_MATURATION</strong></td>
<td align="center">0.0001187</td>
</tr>
</tbody>
</table>

#### PAXgene sample results

<table>
<caption>Table continues below</caption>
<colgroup>
<col width="74%" />
<col width="11%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">NGenes</th>
<th align="center">Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>GO_REGULATION_OF_SECONDARY_METABOLIC_PROCESS</strong></td>
<td align="center">9</td>
<td align="center">Down</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_NEGATIVE_REGULATION_OF_VIRAL_GENOME_REPLICATION</strong></td>
<td align="center">61</td>
<td align="center">Down</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_RESPONSE_TO_TYPE_I_INTERFERON</strong></td>
<td align="center">78</td>
<td align="center">Down</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_CELLULAR_DEFENSE_RESPONSE</strong></td>
<td align="center">53</td>
<td align="center">Down</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_INTERFERON_GAMMA_MEDIATED_SIGNALING_PATHWAY</strong></td>
<td align="center">82</td>
<td align="center">Down</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_CELLULAR_RESPONSE_TO_INTERFERON_GAMMA</strong></td>
<td align="center">112</td>
<td align="center">Down</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_GANGLION_DEVELOPMENT</strong></td>
<td align="center">3</td>
<td align="center">Down</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_RESPIRATORY_BURST</strong></td>
<td align="center">15</td>
<td align="center">Down</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_RESPONSE_TO_INTERFERON_GAMMA</strong></td>
<td align="center">132</td>
<td align="center">Down</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_CELLULAR_RESPONSE_TO_VITAMIN_D</strong></td>
<td align="center">12</td>
<td align="center">Down</td>
</tr>
</tbody>
</table>

<table style="width:92%;">
<colgroup>
<col width="79%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">PValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>GO_REGULATION_OF_SECONDARY_METABOLIC_PROCESS</strong></td>
<td align="center">3.427e-06</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_NEGATIVE_REGULATION_OF_VIRAL_GENOME_REPLICATION</strong></td>
<td align="center">4.641e-05</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_RESPONSE_TO_TYPE_I_INTERFERON</strong></td>
<td align="center">7.852e-05</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_CELLULAR_DEFENSE_RESPONSE</strong></td>
<td align="center">0.0001721</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_INTERFERON_GAMMA_MEDIATED_SIGNALING_PATHWAY</strong></td>
<td align="center">0.0002616</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_CELLULAR_RESPONSE_TO_INTERFERON_GAMMA</strong></td>
<td align="center">0.0002874</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_GANGLION_DEVELOPMENT</strong></td>
<td align="center">0.0005102</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_RESPIRATORY_BURST</strong></td>
<td align="center">0.0006813</td>
</tr>
<tr class="odd">
<td align="center"><strong>GO_RESPONSE_TO_INTERFERON_GAMMA</strong></td>
<td align="center">0.0006942</td>
</tr>
<tr class="even">
<td align="center"><strong>GO_CELLULAR_RESPONSE_TO_VITAMIN_D</strong></td>
<td align="center">0.00123</td>
</tr>
</tbody>
</table>

### MTN-007 gene sets: top 10 results

Here I am comparing the probes in this experiment to significantly differentially expressed probes from MTN-007 9cm biopsies at 7 days.

#### Duodenal sample results

<table style="width:65%;">
<colgroup>
<col width="23%" />
<col width="12%" />
<col width="16%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">NGenes</th>
<th align="center">Direction</th>
<th align="center">PValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>Mtn007Down</strong></td>
<td align="center">765</td>
<td align="center">Down</td>
<td align="center">6.665e-06</td>
</tr>
<tr class="even">
<td align="center"><strong>Mtn007Up</strong></td>
<td align="center">181</td>
<td align="center">Up</td>
<td align="center">0.008987</td>
</tr>
</tbody>
</table>

#### Rectal sample results

<table style="width:64%;">
<colgroup>
<col width="23%" />
<col width="12%" />
<col width="16%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">NGenes</th>
<th align="center">Direction</th>
<th align="center">PValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>Mtn007Down</strong></td>
<td align="center">787</td>
<td align="center">Down</td>
<td align="center">7.12e-06</td>
</tr>
<tr class="even">
<td align="center"><strong>Mtn007Up</strong></td>
<td align="center">191</td>
<td align="center">Down</td>
<td align="center">0.004617</td>
</tr>
</tbody>
</table>

#### PBMC sample results

<table style="width:64%;">
<colgroup>
<col width="23%" />
<col width="12%" />
<col width="16%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">NGenes</th>
<th align="center">Direction</th>
<th align="center">PValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>Mtn007Down</strong></td>
<td align="center">735</td>
<td align="center">Down</td>
<td align="center">0.3501</td>
</tr>
<tr class="even">
<td align="center"><strong>Mtn007Up</strong></td>
<td align="center">152</td>
<td align="center">Down</td>
<td align="center">0.369</td>
</tr>
</tbody>
</table>

#### PAXgene sample results

<table style="width:64%;">
<colgroup>
<col width="23%" />
<col width="12%" />
<col width="16%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th align="center"> </th>
<th align="center">NGenes</th>
<th align="center">Direction</th>
<th align="center">PValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center"><strong>Mtn007Down</strong></td>
<td align="center">675</td>
<td align="center">Down</td>
<td align="center">0.04021</td>
</tr>
<tr class="even">
<td align="center"><strong>Mtn007Up</strong></td>
<td align="center">144</td>
<td align="center">Up</td>
<td align="center">0.7308</td>
</tr>
</tbody>
</table>

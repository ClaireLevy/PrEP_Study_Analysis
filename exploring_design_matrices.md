Exploring design matrices
================

There are 8 Ptids and 2 Visits per Ptid (Enrollment and Visit2)

Here is what the design matrix looks like for the design with no interecept,

~0 + Visit + Ptid

Why are there only 7 Ptids shown? I think because the first level of each parameter is absorbed into the intercept and the because I am using an additive model, the coefficients for the Visits are assuming that the effect is the same for all patients. See here: According to <http://genomicsclass.github.io/book/pages/expressing_design_formula.html>, and replace "Visit" with "Diet" and "Ptid" for "Sex"

Rows 15 and 16 have zeros in all columns except for the first two, which I assume means that they are representing the average of the expression for all Ptids for those visits??

Because there is information on both Visits and I want to compare the average results from the two visits, I will make a contrasts matrix:

contrasts &lt;- makeContrasts(Visit2vsEnrollment = VisitVisit2-VisitEnrollment, levels = no\_int\_design)

and then fit the model to the contrast matrix.

    ##    VisitEnrollment VisitVisit2 PtidCM2299 PtidDA2301 PtidJC2300 PtidJM2297
    ## 1                1           0          0          0          0          1
    ## 2                0           1          0          0          0          1
    ## 3                1           0          0          0          0          0
    ## 4                0           1          0          0          0          0
    ## 5                1           0          1          0          0          0
    ## 6                0           1          1          0          0          0
    ## 7                1           0          0          0          1          0
    ## 8                0           1          0          0          1          0
    ## 9                1           0          0          1          0          0
    ## 10               0           1          0          1          0          0
    ## 11               1           0          0          0          0          0
    ## 12               0           1          0          0          0          0
    ## 13               1           0          0          0          0          0
    ## 14               0           1          0          0          0          0
    ## 15               1           0          0          0          0          0
    ## 16               0           1          0          0          0          0
    ##    PtidLS2298 PtidRC2302 PtidSN2303
    ## 1           0          0          0
    ## 2           0          0          0
    ## 3           1          0          0
    ## 4           1          0          0
    ## 5           0          0          0
    ## 6           0          0          0
    ## 7           0          0          0
    ## 8           0          0          0
    ## 9           0          0          0
    ## 10          0          0          0
    ## 11          0          1          0
    ## 12          0          1          0
    ## 13          0          0          1
    ## 14          0          0          1
    ## 15          0          0          0
    ## 16          0          0          0
    ## attr(,"assign")
    ## [1] 1 1 2 2 2 2 2 2 2
    ## attr(,"contrasts")
    ## attr(,"contrasts")$Visit
    ## [1] "contr.treatment"
    ## 
    ## attr(,"contrasts")$Ptid
    ## [1] "contr.treatment"

There are 8 Ptids and 2 Visits per Ptid (Enrollment and Visit2)

Here is what the design matrix looks like for the design *with* intercept, ~Visit + Ptid

I think the intercept here represents the average of Enrollment and the coefficent "VisitVisit2" represents the increase in the average of Visit2 *over* Enrollment. Because this comparison is already made with this design, I don't need to do a contrast matrix.

    ##    (Intercept) VisitVisit2 PtidCM2299 PtidDA2301 PtidJC2300 PtidJM2297
    ## 1            1           0          0          0          0          1
    ## 2            1           1          0          0          0          1
    ## 3            1           0          0          0          0          0
    ## 4            1           1          0          0          0          0
    ## 5            1           0          1          0          0          0
    ## 6            1           1          1          0          0          0
    ## 7            1           0          0          0          1          0
    ## 8            1           1          0          0          1          0
    ## 9            1           0          0          1          0          0
    ## 10           1           1          0          1          0          0
    ## 11           1           0          0          0          0          0
    ## 12           1           1          0          0          0          0
    ## 13           1           0          0          0          0          0
    ## 14           1           1          0          0          0          0
    ## 15           1           0          0          0          0          0
    ## 16           1           1          0          0          0          0
    ##    PtidLS2298 PtidRC2302 PtidSN2303
    ## 1           0          0          0
    ## 2           0          0          0
    ## 3           1          0          0
    ## 4           1          0          0
    ## 5           0          0          0
    ## 6           0          0          0
    ## 7           0          0          0
    ## 8           0          0          0
    ## 9           0          0          0
    ## 10          0          0          0
    ## 11          0          1          0
    ## 12          0          1          0
    ## 13          0          0          1
    ## 14          0          0          1
    ## 15          0          0          0
    ## 16          0          0          0
    ## attr(,"assign")
    ## [1] 0 1 2 2 2 2 2 2 2
    ## attr(,"contrasts")
    ## attr(,"contrasts")$Visit
    ## [1] "contr.treatment"
    ## 
    ## attr(,"contrasts")$Ptid
    ## [1] "contr.treatment"

Here are results from fitting the model using decideTests(method = "global") vs decideTests(method = "separate") for the design *without* an intercept.

<table style="width:42%;">
<colgroup>
<col width="26%" />
<col width="9%" />
<col width="5%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">variable</th>
<th align="center">down</th>
<th align="center">up</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">Visit2vsEnrollment</td>
<td align="center">70</td>
<td align="center">11</td>
</tr>
</tbody>
</table>

<table style="width:42%;">
<colgroup>
<col width="26%" />
<col width="9%" />
<col width="5%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">variable</th>
<th align="center">down</th>
<th align="center">up</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">Visit2vsEnrollment</td>
<td align="center">70</td>
<td align="center">11</td>
</tr>
</tbody>
</table>

Here are results from fitting the model using decideTests(method = "global") vs decideTests(method = "separate") for the design *with* an intercept.

<table style="width:36%;">
<colgroup>
<col width="16%" />
<col width="9%" />
<col width="9%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">variable</th>
<th align="center">down</th>
<th align="center">up</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">(Intercept)</td>
<td align="center">0</td>
<td align="center">20505</td>
</tr>
<tr class="even">
<td align="center">VisitVisit2</td>
<td align="center">70</td>
<td align="center">11</td>
</tr>
<tr class="odd">
<td align="center">PtidCM2299</td>
<td align="center">281</td>
<td align="center">218</td>
</tr>
<tr class="even">
<td align="center">PtidDA2301</td>
<td align="center">27</td>
<td align="center">26</td>
</tr>
<tr class="odd">
<td align="center">PtidJC2300</td>
<td align="center">65</td>
<td align="center">59</td>
</tr>
<tr class="even">
<td align="center">PtidJM2297</td>
<td align="center">41</td>
<td align="center">24</td>
</tr>
<tr class="odd">
<td align="center">PtidLS2298</td>
<td align="center">153</td>
<td align="center">141</td>
</tr>
<tr class="even">
<td align="center">PtidRC2302</td>
<td align="center">41</td>
<td align="center">37</td>
</tr>
<tr class="odd">
<td align="center">PtidSN2303</td>
<td align="center">22</td>
<td align="center">14</td>
</tr>
</tbody>
</table>

<table style="width:36%;">
<colgroup>
<col width="16%" />
<col width="9%" />
<col width="9%" />
</colgroup>
<thead>
<tr class="header">
<th align="center">variable</th>
<th align="center">down</th>
<th align="center">up</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="center">(Intercept)</td>
<td align="center">0</td>
<td align="center">20505</td>
</tr>
<tr class="even">
<td align="center">VisitVisit2</td>
<td align="center">121</td>
<td align="center">55</td>
</tr>
<tr class="odd">
<td align="center">PtidCM2299</td>
<td align="center">593</td>
<td align="center">463</td>
</tr>
<tr class="even">
<td align="center">PtidDA2301</td>
<td align="center">141</td>
<td align="center">96</td>
</tr>
<tr class="odd">
<td align="center">PtidJC2300</td>
<td align="center">292</td>
<td align="center">204</td>
</tr>
<tr class="even">
<td align="center">PtidJM2297</td>
<td align="center">258</td>
<td align="center">213</td>
</tr>
<tr class="odd">
<td align="center">PtidLS2298</td>
<td align="center">404</td>
<td align="center">421</td>
</tr>
<tr class="even">
<td align="center">PtidRC2302</td>
<td align="center">216</td>
<td align="center">224</td>
</tr>
<tr class="odd">
<td align="center">PtidSN2303</td>
<td align="center">174</td>
<td align="center">195</td>
</tr>
</tbody>
</table>

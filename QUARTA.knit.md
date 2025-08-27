

---
title: "Microarray Analysis"
output:
  html_document:
    css: styles.css
---




### Matrice "ID delle sonde" - "ID dei campioni" e selezione dei campioni (Primi 12)

![](img1.png){width=180px height=auto}


``` r
A <- getGEO("GSE76999", GSEMatrix = TRUE, getGPL = FALSE)
```

```
## Found 1 file(s)
```

```
## GSE76999_series_matrix.txt.gz
```

``` r
B <- A[[1]]

varLabels(B)
```

```
##  [1] "title"                   "geo_accession"           "status"                 
##  [4] "submission_date"         "last_update_date"        "type"                   
##  [7] "channel_count"           "source_name_ch1"         "organism_ch1"           
## [10] "characteristics_ch1"     "characteristics_ch1.1"   "characteristics_ch1.2"  
## [13] "treatment_protocol_ch1"  "growth_protocol_ch1"     "molecule_ch1"           
## [16] "extract_protocol_ch1"    "label_ch1"               "label_protocol_ch1"     
## [19] "taxid_ch1"               "hyb_protocol"            "scan_protocol"          
## [22] "description"             "data_processing"         "data_processing.1"      
## [25] "data_processing.2"       "platform_id"             "contact_name"           
## [28] "contact_email"           "contact_department"      "contact_institute"      
## [31] "contact_address"         "contact_city"            "contact_zip/postal_code"
## [34] "contact_country"         "supplementary_file"      "data_row_count"         
## [37] "relation"                "relation.1"              "age:ch1"                
## [40] "strain:ch1"              "tissue:ch1"
```

``` r
B$organism_ch1
```

```
##  [1] "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus"
##  [7] "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus"
## [13] "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus"
## [19] "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus"
## [25] "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus"
## [31] "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus" "Mus musculus"
```

``` r
B$title
```

```
##  [1] "Monocyte extracted from adult (wk6-12) Bone Marrow, biological replicate 1"                                     
##  [2] "Monocyte extracted from adult (wk6-12) Bone Marrow, biological replicate 2"                                     
##  [3] "Monocyte extracted from adult (wk6-12) Bone Marrow, biological replicate 3"                                     
##  [4] "Monocyte extracted from adult (wk6-12) Bone Marrow, biological replicate 4"                                     
##  [5] "Monocyte extracted from E15.5 Fetal Liver, biological replicate 1"                                              
##  [6] "Monocyte extracted from E15.5 Fetal Liver, biological replicate 2"                                              
##  [7] "Monocyte extracted from E15.5 Fetal Liver, biological replicate 3"                                              
##  [8] "Monocyte extracted from E15.5 Fetal Liver, biological replicate 4"                                              
##  [9] "Macrophage extracted from E12.5 Yolk Sac, biological replicate 1"                                               
## [10] "Macrophage extracted from E12.5 Yolk Sac, biological replicate 2"                                               
## [11] "Macrophage extracted from E12.5 Yolk Sac, biological replicate 3"                                               
## [12] "Macrophage extracted from E12.5 Yolk Sac, biological replicate 4"                                               
## [13] "Alveolar Macrophage extracted from adult (wk6-12) mice via Bronchoalveolar lavage, biological replicate 1"      
## [14] "Alveolar Macrophage extracted from adult (wk6-12) mice via Bronchoalveolar lavage, biological replicate 2"      
## [15] "Alveolar Macrophage extracted from adult (wk6-12) mice via Bronchoalveolar lavage, biological replicate 3"      
## [16] "Alveolar Macrophage extracted from adult (wk6-12) mice via Bronchoalveolar lavage, biological replicate 4"      
## [17] "Alveolar Macrophage derived from transferred Bone Marrow Monocytes, 6 wks post-transfer, biological replicate 1"
## [18] "Alveolar Macrophage derived from transferred Bone Marrow Monocytes, 6 wks post-transfer, biological replicate 2"
## [19] "Alveolar Macrophage derived from transferred Bone Marrow Monocytes, 6 wks post-transfer, biological replicate 3"
## [20] "Alveolar Macrophage derived from transferred Bone Marrow Monocytes, 6 wks post-transfer, biological replicate 4"
## [21] "Alveolar Macrophage derived from transferred Fetal Liver Monocytes, 6 wks post-transfer, biological replicate 1"
## [22] "Alveolar Macrophage derived from transferred Fetal Liver Monocytes, 6 wks post-transfer, biological replicate 2"
## [23] "Alveolar Macrophage derived from transferred Fetal Liver Monocytes, 6 wks post-transfer, biological replicate 3"
## [24] "Alveolar Macrophage derived from transferred Fetal Liver Monocytes, 6 wks post-transfer, biological replicate 4"
## [25] "Alveolar Macrophage derived from transferred Yolk Sac Macrophages, 6 wks post-transfer, biological replicate 1" 
## [26] "Alveolar Macrophage derived from transferred Yolk Sac Macrophages, 6 wks post-transfer, biological replicate 2" 
## [27] "Alveolar Macrophage derived from transferred Yolk Sac Macrophages, 6 wks post-transfer, biological replicate 3" 
## [28] "Alveolar Macrophage derived from transferred Yolk Sac Macrophages, 6 wks post-transfer, biological replicate 4" 
## [29] "Alveolar Macrophage derived from transferred Alveolar macrophages, 6 wks post-transfer, biological replicate 1" 
## [30] "Alveolar Macrophage derived from transferred Alveolar macrophages, 6 wks post-transfer, biological replicate 2" 
## [31] "Alveolar Macrophage derived from transferred Alveolar macrophages, 6 wks post-transfer, biological replicate 3" 
## [32] "Alveolar Macrophage derived from transferred Alveolar macrophages, 6 wks post-transfer, biological replicate 4" 
## [33] "Alveolar Macrophage extracted from 6 wk old wild type mice via Bronchoalveolar lavage, biological replicate 1"  
## [34] "Alveolar Macrophage extracted from 6 wk old wild type mice via Bronchoalveolar lavage, biological replicate 2"  
## [35] "Alveolar Macrophage extracted from 6 wk old wild type mice via Bronchoalveolar lavage, biological replicate 3"  
## [36] "Alveolar Macrophage extracted from 6 wk old wild type mice via Bronchoalveolar lavage, biological replicate 4"
```

``` r
C <- exprs(B)

C[1:5,1:12]
```

```
##          GSM2042244 GSM2042245 GSM2042246 GSM2042247 GSM2042248 GSM2042249 GSM2042250 GSM2042251
## 10338001  12.883736  12.710357  12.808904  12.728285  12.670743  12.582576  12.728665  12.701661
## 10338002   5.478638   4.836992   5.354476   5.311100   5.128454   5.158269   5.576625   5.174163
## 10338003  11.565683  11.007533  11.348052  11.232528  10.989176  11.017759  11.300946  11.105487
## 10338004   9.784679   9.218110   7.900875   9.508223   7.373025   7.647630   9.188661   9.042846
## 10338005   2.179659   1.997411   2.215015   2.134441   2.062177   2.174181   2.091476   2.102721
##          GSM2042252 GSM2042253 GSM2042254 GSM2042255
## 10338001  12.845415  12.763705  12.760986  12.609271
## 10338002   4.967542   5.210838   5.116310   4.890626
## 10338003  11.282599  11.216054  11.144170  10.939133
## 10338004   7.527401   9.193056   7.072794   9.433758
## 10338005   2.073256   2.095818   2.140202   2.067220
```

``` r
boxplot(C[1:2,1:12], las=2, cex.axis = 0.7)
```

<img src="QUARTA_files/figure-html/unnamed-chunk-3-1.png" width="672" />





### Differential Expression Analysis by Limma





















































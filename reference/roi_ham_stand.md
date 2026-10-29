# Return a list of merged ROIs made up of the atomic ROIs in the Hammer's atlas.

Return a list of merged ROIs made up of the atomic ROIs in the Hammer's
atlas.

## Usage

``` r
roi_ham_stand()
```

## Value

A list of lists, where each list is an ROI (e.g.) frontal lobe that
specifies the atomic ROIs from the atlas that make it up.

## References

Hammers, Alexander, Richard Allom, Matthias J. Koepp, Samantha L. Free,
Ralph Myers, Louis Lemieux, Tejal N. Mitchell, David J. Brooks, and John
S. Duncan. 2003. Three-dimensional Maximum Probability Atlas of the
Human Brain, with Particular Reference to the Temporal Lobe. Human Brain
Mapping 19 (4): 224-247. doi:10.1002/hbm.10123

## See also

Other ROI definitions:
[`roi_ham_full`](https://docs.ropensci.org/tacmagic/reference/roi_ham_full.md),
[`roi_ham_pib`](https://docs.ropensci.org/tacmagic/reference/roi_ham_pib.md)

## Examples

``` r
roi_ham_stand()
#> $leftfrontal
#>  [1] "FL_mid_fr_G_l"       "FL_precen_G_l"       "FL_strai_G_l"       
#>  [4] "FL_OFC_AOG_l"        "FL_inf_fr_G_l"       "FL_sup_fr_G_l"      
#>  [7] "FL_OFC_MOG_l"        "FL_OFC_LOG_l"        "FL_OFC_POG_l"       
#> [10] "Subgen_antCing_l"    "Subcall_area_l"      "Presubgen_antCing_l"
#> 
#> $rightfrontal
#>  [1] "FL_mid_fr_G_r"       "FL_precen_G_r"       "FL_strai_G_r"       
#>  [4] "FL_OFC_AOG_r"        "FL_inf_fr_G_r"       "FL_sup_fr_G_r"      
#>  [7] "FL_OFC_MOG_r"        "FL_OFC_LOG_r"        "FL_OFC_POG_r"       
#> [10] "Subgen_antCing_r"    "Subcall_area_r"      "Presubgen_antCing_r"
#> 
#> $lefttemporal
#>  [1] "Hippocampus_l"     "Amygdala_l"        "Ant_TL_med_l"     
#>  [4] "Ant_TL_inf_lat_l"  "G_paraH_amb_l"     "G_sup_temp_post_l"
#>  [7] "G_tem_midin_l"     "G_fus_l"           "Post_TL_l"        
#> [10] "G_sup_temp_ant_l" 
#> 
#> $righttemporal
#>  [1] "Hippocampus_r"     "Amygdala_r"        "Ant_TL_med_r"     
#>  [4] "Ant_TL_inf_lat_r"  "G_paraH_amb_r"     "G_sup_temp_post_r"
#>  [7] "G_tem_midin_r"     "G_fus_r"           "Post_TL_r"        
#> [10] "G_sup_temp_ant_r" 
#> 
#> $leftparietal
#> [1] "PL_postce_G_l" "PL_sup_pa_G_l" "PL_rest_l"    
#> 
#> $rightparietal
#> [1] "PL_postce_G_r" "PL_sup_pa_G_r" "PL_rest_r"    
#> 
#> $leftoccipital
#> [1] "OL_rest_lat_l" "OL_ling_G_l"   "OL_cuneus_l"  
#> 
#> $rightoccipital
#> [1] "OL_rest_lat_r" "OL_ling_G_r"   "OL_cuneus_r"  
#> 
#> $leftcingulate
#> [1] "G_cing_ant_l"  "G_cing_post_l"
#> 
#> $rightcingulate
#> [1] "G_cing_ant_r"  "G_cing_post_r"
#> 
#> $frontal
#>  [1] "FL_mid_fr_G_l"       "FL_precen_G_l"       "FL_strai_G_l"       
#>  [4] "FL_OFC_AOG_l"        "FL_inf_fr_G_l"       "FL_sup_fr_G_l"      
#>  [7] "FL_OFC_MOG_l"        "FL_OFC_LOG_l"        "FL_OFC_POG_l"       
#> [10] "Subgen_antCing_l"    "Subcall_area_l"      "Presubgen_antCing_l"
#> [13] "FL_mid_fr_G_r"       "FL_precen_G_r"       "FL_strai_G_r"       
#> [16] "FL_OFC_AOG_r"        "FL_inf_fr_G_r"       "FL_sup_fr_G_r"      
#> [19] "FL_OFC_MOG_r"        "FL_OFC_LOG_r"        "FL_OFC_POG_r"       
#> [22] "Subgen_antCing_r"    "Subcall_area_r"      "Presubgen_antCing_r"
#> 
#> $temporal
#>  [1] "Hippocampus_l"     "Amygdala_l"        "Ant_TL_med_l"     
#>  [4] "Ant_TL_inf_lat_l"  "G_paraH_amb_l"     "G_sup_temp_post_l"
#>  [7] "G_tem_midin_l"     "G_fus_l"           "Post_TL_l"        
#> [10] "G_sup_temp_ant_l"  "Hippocampus_r"     "Amygdala_r"       
#> [13] "Ant_TL_med_r"      "Ant_TL_inf_lat_r"  "G_paraH_amb_r"    
#> [16] "G_sup_temp_post_r" "G_tem_midin_r"     "G_fus_r"          
#> [19] "Post_TL_r"         "G_sup_temp_ant_r" 
#> 
#> $parietal
#> [1] "PL_postce_G_l" "PL_sup_pa_G_l" "PL_rest_l"     "PL_postce_G_r"
#> [5] "PL_sup_pa_G_r" "PL_rest_r"    
#> 
#> $occipital
#> [1] "OL_rest_lat_l" "OL_ling_G_l"   "OL_cuneus_l"   "OL_rest_lat_r"
#> [5] "OL_ling_G_r"   "OL_cuneus_r"  
#> 
#> $cingulate
#> [1] "G_cing_ant_l"  "G_cing_post_l" "G_cing_ant_r"  "G_cing_post_r"
#> 
#> $cerebellum
#> [1] "Cerebellum_l" "Cerebellum_r"
#> 
#> $totalcortical
#>  [1] "FL_mid_fr_G_l"       "FL_precen_G_l"       "FL_strai_G_l"       
#>  [4] "FL_OFC_AOG_l"        "FL_inf_fr_G_l"       "FL_sup_fr_G_l"      
#>  [7] "FL_OFC_MOG_l"        "FL_OFC_LOG_l"        "FL_OFC_POG_l"       
#> [10] "Subgen_antCing_l"    "Subcall_area_l"      "Presubgen_antCing_l"
#> [13] "FL_mid_fr_G_r"       "FL_precen_G_r"       "FL_strai_G_r"       
#> [16] "FL_OFC_AOG_r"        "FL_inf_fr_G_r"       "FL_sup_fr_G_r"      
#> [19] "FL_OFC_MOG_r"        "FL_OFC_LOG_r"        "FL_OFC_POG_r"       
#> [22] "Subgen_antCing_r"    "Subcall_area_r"      "Presubgen_antCing_r"
#> [25] "Hippocampus_l"       "Amygdala_l"          "Ant_TL_med_l"       
#> [28] "Ant_TL_inf_lat_l"    "G_paraH_amb_l"       "G_sup_temp_post_l"  
#> [31] "G_tem_midin_l"       "G_fus_l"             "Post_TL_l"          
#> [34] "G_sup_temp_ant_l"    "Hippocampus_r"       "Amygdala_r"         
#> [37] "Ant_TL_med_r"        "Ant_TL_inf_lat_r"    "G_paraH_amb_r"      
#> [40] "G_sup_temp_post_r"   "G_tem_midin_r"       "G_fus_r"            
#> [43] "Post_TL_r"           "G_sup_temp_ant_r"    "PL_postce_G_l"      
#> [46] "PL_sup_pa_G_l"       "PL_rest_l"           "PL_postce_G_r"      
#> [49] "PL_sup_pa_G_r"       "PL_rest_r"           "OL_rest_lat_l"      
#> [52] "OL_ling_G_l"         "OL_cuneus_l"         "OL_rest_lat_r"      
#> [55] "OL_ling_G_r"         "OL_cuneus_r"         "G_cing_ant_l"       
#> [58] "G_cing_post_l"       "G_cing_ant_r"        "G_cing_post_r"      
#> 
```

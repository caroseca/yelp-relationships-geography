# yelp-relationships-geography

01-get-data-by-metro.ipynb
	- IN: YelpChallengeWMetros_Clean.csv (our cleaned version of yelp_academic_dataset_business.csv); yelp_academic_dataset_review.csv (not included in GitHub, too large)
	- OUT: small_reviews_urbcomp/yelp_academic_dataset_reviews_METRO.csv for each METRO


02-do-text-mining.ipynb
	- IN: relationships/Relationships_ATUS_custom_v2.txt; small_reviews_urbcomp/yelp_academic_dataset_reviews_METRO.csv for each METRO
	- OUT: output_urbcomp/METRO_counts_v2.csv for each METRO; output_urbcomp/METRO_counts_ungrouped_v2.csv for each METRO


03-process-counts.ipynb
	- IN: output/METRO_counts_v2.csv for each METRO; output/METRO_counts_ungrouped_v2.csv for each METRO; relationships/Relationships_ATUS_custom_v2_binned.txt; categories.json; yelp_academic_dataset_business_clean.csv (REPLACE WITH YelpChallengeWMetros_Clean.csv)
	- OUT: output/METRO_counts_final_v2.csv and output/METRO_counts_norm_final_v2.csv for each METRO


04-output-files.ipynb
	- IN: files from 03
	- OUT: final_output_urbcomp/all_counts_final_v2, final_output_urbcomp/all_counts_norm_final_v2, final_output_urbcomp/num_businesses

# Yelp, Relationships, & Geography

Update 2/13/24: Note that the version of this codebase was forked and edited by students in University of Michigan, SI699. The data was trimmed for ease of use and brevity.

---

The original data must be downloaded from the [Yelp Open Dataset](https://www.yelp.com/dataset) as it is too big to upload to GitHub. The dataset is provided in JSON format, but you can use the [example code provided by Yelp](https://github.com/Yelp/dataset-examples/blob/master/json_to_csv_converter.py) to convert them to CSV. The only file you need from the dataset to run our analysis is `yelp_academic_dataset_review.csv` (after converting to CSV). Our file included here called `YelpChallengeWMetros_Clean.csv` is a cleaned version of `yelp_academic_dataset_business.csv` that you would get from downloading the dataset and running it through the converter.

The file `01-get-data-by-metro.ipynb` contains code for taking the raw reviews data and creating new files in the `small_reviews_urbcomp/` directory that divide the reviews by metro area for easier processing. Due to large file sizes, we only include the file for Boulder, CO (`yelp_academic_dataset_reviews_Boulder.csv`) in this repository.

The file `02-do-text-mining.ipynb` processes the reviews from the previous file and outputs raw relationship word counts in the `output_urbcomp/` directory.

The file `03-process-counts.ipynb` processes the raw word counts to get intermediate counts (including normalized counts) which are also stored in the `output_urbcomp/` directory.

The file `04-output-files.ipynb` outputs the final, fully processed results files as reflected in the paper. These files are located in the directory `final_output_urbcomp/` and include `all_counts_final_v2.csv` (unnormalized word counts per POI, for all metro areas), `all_counts_norm_final_v2.csv` (the normalized version of the previous file), and `num_businesses.csv` (for each relationship word, the number of POIs with at least one occurrence in their reviews).

#### Notes for if you want to continue with new Yelp Open Dataset data
Note that this repository does not contain the most recent version of the [Yelp Open Dataset](https://www.yelp.com/dataset).

If you want to continue this work beyond the tutorial, you will have to get the data and then convert it to csv. If a standard json to csv procedure doesn't work on the files, then you will want to use this updated version of Yelp's json to csv convertor. Note that this update helps it work with Python 3: https://github.com/Yelp/dataset-examples/pull/46/files

Additionally, on the Yelp Open Dataset homepage, it claims that there are 11 metro areas, but in the FAQ it only claims 10 are in the dataset. In order to accurately identify which metro areas are in the dataset, we recommend using the [USPS Crosswalk](https://www.huduser.gov/portal/datasets/usps_crosswalk.html) to get a better idea of which metros are included.
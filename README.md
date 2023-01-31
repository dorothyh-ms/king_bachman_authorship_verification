# Authorship Verification of Stephen King's "Bachman" Books

## Paper 

This repository contains the code accompanying the following paper: 
"The Authorship of Stephen King’s Books Written Under the Pseudonym “Richard Bachman”: A Stylometric Analysis", by Dorothy Modrall Sperling, Vincent Neyt, and Mike Kestemont.

> _Abstract_: Between 1977 and 1984, Stephen King published five novels under the pseudonym “Richard Bachman”. Reviewers noted similarities between King’s and Bachman’s writing styles when _Thinner_ (1984) was published, ultimately leading to King’s unmasking. In this paper, we investigate whether computational authorship analysis techniques can correctly identify King as the author of the Bachman books out of a selection of contemporary candidate authors – Dean Koontz, Peter Straub, and Thomas Harris. We also perform a post-hoc analysis of the use of pop-culture references and brand names in Bachman, King, Koontz, Straub, and Harris novels, based on comments in reviews of Bachman and King novels. The references extracted from the Bachman books occurred significantly more often in King’s texts than in the others’, showing that attentive readers could have “heard King’s voice” in the Bachman books through what a reviewer denigratingly called King’s “compulsion to list brand-name products and his affinity for pop-cult teenage junk”.

## Code

This repository contains 7 Jupyter notebooks, which contain the Python and R code used for our analysis: 
- `0-authorship-data-prep`: Python code for dividing each book's TXT file into 1,000-, 5,000-, and 10,000-token segments. The notebook also contains code to get the 300 most common words (used for our PCA analysis section) and descriptive statistics (wordcount, type-token ratios) on each book. 
- `1-o2-classifier`: Python code to get the cosine similarity (based on a large bootstrapped feature space) of each Bachman segment to a randomly-sampled segment by each author. Cosine distances are converted to ranks, where 1=most similar, and 4=least similar. 
- `2a-author_ranks_statistical_testing`: R code to test the significance of correlations between author and similarity ranking to Bachman segments.
- `2b-authors_ranks_proportions`: Python code to convert raw counts of similarity rankings extracted in `1-o2-classifier` to proportions.
- `3-PCA_functionwords`: Python code to vectorize full texts using function words as features (excluded words begin with a "#". Personal pronouns are also excluded and end with a "-"). PCA is performed on these vectors to visualize resulting clusters alongside function words. 
- `4-cultural_references`: Python code to turn full texts into SpaCy docs and count the number of cultural references (extracted manually from Bachman books) in 10,000-token randomly-sampled segments in each doc. 
- `5-cultural_references_statistical_testing`: R code to test whether cultural reference counts are singificantly higher in Bachman segments compared to segments by other authors in the corpus (King, Koontz, Straub, and Harris). Entity counts in King segments are also compared to entity counts in Koontz, Straub, and Harris segments. 

## Data

Due to copyright restrictions, the full texts and segments of the King, Straub, Harris, and Koontz books used in our experiments are not shared.

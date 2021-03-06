# Genetics to Therapuetics
Using RNA-seq data from cancer patients to determine optimal therapuetic with machine learning

# Cancer and Chemotherapuetics

Roughly 1.8 million adults are diagnosed with cancer in the United States each year. Less than 1%, or about 16,000 of those cases are ages 0-19. Most pediatric cancers are rare and as such are difficult to study. For example, there are roughly 100 cases of hepatoblastoma (pediatric liver cancer) in the United States this year. With such (relatively) small sample numbers, and less research being done than for adult cancer its important to find ways to pull information from adult cancer and be able to generalize it to pediatric cancer. 

Chemotherapy is generally a non-targeted, non-specific treatment. What if there is something broadly in the gene expression of a patient that may point to what chemotherapuetic may be best for them? Developing a robust methodology to could minimize bad outcomes, side effects, and could potentially be generalized to smaller cancer populations like hepatoblastoma patients.

In this project, adult kidney cancer data is collected and analyzed, in part because like hepatoblastoma, it is sometimes wnt-beta catenin driven. 

RNA-seq data and clinical data is pulled from the Cancer Genome Atlas.

# Feature Reduction of RNA-seq Data
![RNA-seq data for one drug of interest](https://github.com/thedinak/Genetics-to-Therapuetics/blob/master/Jupyter_notebooks/gem_heatmap.jpg)
RNA-seq data from the Cancer Genome Atlas provides over 60,000 genes per patient. In order to do accurate and robust prediction, these features need to be reduced, to avoid a highly overfit model. This project provides code to explore various strategies for feature reduction of RNA-seq data, including correlation to the outcome, amount of variability in the gene, PCA and mini-batch sparse PCA. After combining these various strategies, the user can evaluate the best methodology based on their metric of choice.  

Use of feature reduction improved accuracy, recall and precision in the example kidney cancer dataset, although different methodologies were better for different metrics, and were also dependent on the drug given. 

Some limitations of this work: it does not account for the fact that patients are often on multiple medications at once, kidney data sample sizes were fairly small for accurate PCA representation. 

# How to run the script

The following will allow the user to an example data analysis with kidney cancer data.

1. Clone the repository `git clone https://github.com/thedinak/genetics_to_therapuetics.git`

2. Go into the folder `cd genetics_to_therapuetics`

3. Install requirements `pip install -r requirements.txt`

4. Run `python main.py`, follow the command-line instructions.

To run a similar analysis for another cancer type, the user can change the kidney_filters_table in the [example_variables](https://github.com/thedinak/Genetics_to_Therapuetics/blob/master/example_variables.py) file to a filter that reflect the data they would like to collect. 

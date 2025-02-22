# Machine Learning and Genetic Diseases
# Proposal Video

# Introduction
Life’s foundation is reproduction—genetic information passed down with small changes. Over time, mutations have shaped human evolution, sometimes leading to beneficial adaptations while others cause genetic diseases. Genetic disorders affect 2% to 5% of all childbirths are diagnosed with genetic disorders and may lead to 5% to 50% of deaths in childhood; these disorders can be inherited, arise spontaneously, or be influenced by environmental factors [5, 11]. Cystic fibrosis is an autosomal recessive disorder requiring both parents to be carriers [6]. In contrast, mutations like p53, linked to cancer, may occur spontaneously [7]. Some conditions, like type 2 diabetes, develop due to external factors such as diet or prenatal substance exposure [1].
## Dataset
Our project analyzes 22,000 young patients with genetic disorders, categorizing key features into hereditary, spontaneous mutations, and epigenetic influences to investigate their impact.
1. Genes in Mother’s Side - Hereditary
2. Inherited from Father - Hereditary
3. Maternal Gene - Hereditary
4. Paternal Gene - Hereditary
5. Follow-Up - Neither
6. Gender - Hereditary
7. Birth Asphyxia - Epigenetic
8. Place of Birth - Epigenetic
9. Folic Acid Levels - Epigenetic & Spontaneous Mutation
10. H/O Serious Maternal Illness - Epigenetic
11. H/O Radiation Exposure - Spontaneous Mutation
12. H/O Substance Abuse - Epigenetic
13. Assisted Conception - Epigenetic & Spontaneous Mutation
14. No. of Previous Abortions - Hereditary
15. Birth Defect - Hereditary

# Problem Definition:
In healthcare, “models can provide automated prediction, as well as can perform assistive roles for medical experts” [2]. Using machine learning models in predicting genetic diseases has proven to “have increased predictive capabilities for the risk of complex diseases” compared to other risk assessment tests such as polygenic risk scores [4, 8]. Understanding the cause of a patient’s disorder aids in precision and preventative medicine, allowing for personalized care and potential disease prevention through targeted treatments based on an individual’s genetic profile [10, 9]. We aim to create a model that can predict an individual's risk of certain genetic diseases based on given factors and identify possible associated causes for these diseases.

# Methods:
## Preprocessing:
K-Nearest Neighbors Imputation:
- sklearn.impute.KNNImputer can be used for fields like Blood Cell Count, White Blood Cell Count if they are missing.

Handling Misspellings and Abbreviations:
- Fields like Parental Consent and Birth Asphyxia may need fuzzywuzzy for misspellings and MedSpacy for standardization.

Word Embeddings:
- BERT can transform ostensibly useless data into meaningful data, like location of birth.

## Models:
Random Forest:
- sklearn.ensemble.RandomForestClassifier can create an ensemble model capable of finding relationships, though not as deep or recursive as those in a neural network.

Neural Network:
- PyTorch can be used to build deep Neural Networks capable of finding more intricate relationships.

K-Means Clustering (Unsupervised Model):
- sklearn.cluster.KMeans can cluster patients by health conditions and risk factors, providing information about key attributes and potentially aiding other models, despite its limitations.
- Using K-means would be useful in our case since “Unsupervised learning algorithms are especially useful to detect patterns in data sets that have large amounts of data points” [11]

# Results and Discussion
Accuracy, Precision, Recall, and F1-score are standard ML metrics, but in medical data, minimizing false negatives is our priority

Silhouette Score - This metric is the standard one for gauging how well a clustering algorithm, in our case K-Means, performed. 

AUC-ROC Curve - This will help figure out how well the model differentiates between different disorders.

# Goals:
Create an accurate machine learning model and also gather information about the genetic disorders that can help researchers and medical professionals.

To keep the models lightweight for and for sustainability, not excessively overusing LLMs

It is important that our model does not output biased results where it is more accurate toward a specific gender or race

Given the nature of genetics we predict the Neural Network will do the best, with the Random Forest possibly lacking the necessary robustness for this task. The clustering might highlight a few important attributes, but may struggle to convey the full picture.

# References
[1] A. T. Hattersley and S. Ellard, "Monogenic Diabetes: What It Teaches Us on the Common Forms of Diabetes," Endocrine Reviews, vol. 37, no. 3, pp. 190–222, Jun. 2016. [Online]. Available: https://academic.oup.com/edrv/article/37/3/190/2354693

[2] A. Raza et al., "Predicting Genetic Disorder and Types of Disorder Using Chain Classifier Approach," Genes, vol. 14, no. 1, p. 71, Dec. 2022. [Online]. Available: https://doi.org/10.3390/genes14010071

[3] Advances in Distributed Computing and Artificial Intelligence Journal : 9, Regular Issue 1, 2020, Advances in Distributed Computing and Artificial Intelligence Journal. - Quadrimestrale = Four-monthly, vol. 9, regular issue, no. 1, pp. 1–120, Feb. 2025. [Online]. Available: https://www.torrossa.com/en/resources/an/5010975

[4] Exploring the application of deep learning methods for polygenic risk prediction, BMC Medical Genomics, vol. 13, no. 1, pp. 1–12, Dec. 2020. [Online]. Available: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10760287/

[5] J. Zarocostas, "Serious birth defects kill at least three million children a year," BMJ, vol. 332, no. 7536, p. 226, Feb. 2006. [Online]. Available: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1360426/

[6] M. S. Castellani et al., "Cystic Fibrosis-Related Diabetes (CFRD): Overview of Associated Genetic Factors," International Journal of Molecular Sciences, vol. 22, no. 6, p. 3136, Mar. 2021. [Online]. Available: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8005125/

[7] M. G. Goggins et al., "Genetics and Genetic Testing in Pancreatic Cancer," Gastroenterology, vol. 149, no. 3, pp. 676–689, Sep. 2015. [Online]. Available: https://www.gastrojournal.org/article/S0016-5085(15)01089-6/fulltext

[8] Machine Learning Models of Polygenic Risk for Enhanced Prediction of Alzheimer's Disease, Neurology: Genetics, vol. 8, no. 1, pp. e200120, Feb. 2022. [Online]. Available: https://www.neurology.org/doi/10.1212/NXG.0000000000200120

[9] Personalized Medicine, National Human Genome Research Institute, [Online]. Available: https://www.genome.gov/genetics-glossary/Personalized-Medicine

[10] Precision Medicine, U.S. Food and Drug Administration, [Online]. Available: https://www.fda.gov/medical-devices/in-vitro-diagnostics/precision-medicine

[11] S. Rauschert, K. Raubenheimer, P. E. Melton, and R. C. Huang, "Machine learning and clinical epigenetics: a review of challenges for diagnosis and classification," Clinical Epigenetics, vol. 12, no. 1, Apr. 2020. [Online]. Available: https://doi.org/10.1186/s13148-020-00842-4

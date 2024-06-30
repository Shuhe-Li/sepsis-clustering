# Identifying Sepsis Phenotypes With K-Means Clustering Using A Large Public Database
ECMM445 (Learning from Data) Cousework Project created by Shuhe Li

## Backgroud
Sepsis is a life-threatening organ dysfunction led by a dysregulated host response to infection (Singer, Deutschman and Seymour, 2016). Sepsis represents a leading cause of death in intensive care units (ICU), as there is an annual rate of 48.9 million cases of sepsis worldwide, of which 11.1 million patients died, comprising 19.7% of all deaths globally (Rudd et al., 2020). 

Despite the advanced life-support techniques in the ICU, the lack of definite therapies has remained a vital issue because of the heterogeneity of septic patients. The fact that sepsis comprises a multidimensional array of infectious etiologies and clinical features has impeded the effectiveness of guideline-driven management, as guidelines only reflect the needs of the “average” patient (Liu et al., 2020). However, for patients showing certain phenotypes, those treatments may fail and result in undesirable outcomes. Hence, it is crucial to identify phenotypes of sepsis so that targeted treatment strategies can be established towards corresponding patients to improve overall survival.

A body of research has explored the phenotypes of sepsis utilising various clustering algorithms, including K-means (Seymour et al., 2019), spectral clustering (Liu et al., 2020), and hierarchical clustering (Papin et al., 2021), enabling the feasibility of my research proposal. Therefore, I intended to explore the phenotypes of sepsis patients based on clinical variables with K-means clustering utilising the Medical Information Mart for Intensive Care (MIMIC)-IV database.

## Study Diagram
![image](https://github.com/Shuhe-Li/sepsis-clustering/assets/39095779/9e1618a0-dc45-472d-ac3f-68f190cd5e5b)

## Feature Selection
![image](https://github.com/Shuhe-Li/sepsis-clustering/assets/39095779/9a2b6855-f08c-4d62-a6f5-07916ef1401f)

## Results
A total of 23,374 septic patients were included in the study. Three clusters were finally determined, as the Elbow method suggested that the inertia decreased dramatically before K = 3 and then slowed down afterwards. Additionally, silhouette analysis demonstrated that the average silhouette score was the highest when K = 2 (0.447), followed by K = 3 (0.397) and K = 5 (0.345), indicating that three clusters might be the optimal result combined with the Elbow method. 

13,927 patients were labelled as Cluster 1, followed by Cluster 2 (7,047) and Cluster 0 (2,400). Patients in Cluster 0 were the youngest (60 years), but they demonstrated the most severe signs of inflammation (WBC: 21.18) and organ dysfunction, including liver (ALT: 756.56), kidney (creatinine: 3.52), and circulatory dysfunction (lactate: 6.48). Cluster 1 showed the lowest severity score (SOFA score: 3.2) and shortest length of stay in the ICU (5.31 days). Cluster 2 was the eldest (75.5 years), although the severity of organ dysfunction was less critical compared to Cluster 0. Cluster 1 demonstrated the best survival outcome, whereas Cluster 0 manifested the worst 28-day survival. 

Figure 1. Results of K-means clustering. (A) The cluster plot with two-dimensional PCA components (K=3); (B) The Elbow method using inertia; (C) Silhouette analysis for three clusters; (D) 28-day Kaplan-Meier survival plot of three clusters.
![image](https://github.com/Shuhe-Li/sepsis-clustering/assets/39095779/ea0dcc83-47a0-46a5-851a-0c2b3b512b6f)


## Conclusion
Three phenotypes were identified among 23,374 septic patients based on 36 clinical variables within the first 24 hours after ICU admission, and these phenotypes demonstrated distinct clinical characteristics and outcomes.

## Reference
Johnson, A.E.W. et al. (2023) ‘MIMIC-IV, a freely accessible electronic health record dataset’, Scientific Data, 10(1). doi:https:http://sci-hub.se/10.1038/s41597-022-01899-x.

Liu, R. et al. (2020) ‘Spectral clustering of risk score trajectories stratifies sepsis patients by clinical outcome and interventions received’, eLife, 9, p. e58142. doi:https:http://sci-hub.se/10.7554/elife.58142.

Papin, G. et al. (2021) ‘Clinical and biological clusters of sepsis patients using hierarchical clustering’, PLOS ONE. Edited by M. Crivellari, 16(8), p. e0252793. doi:https:http://sci-hub.se/10.1371/journal.pone.0252793.

Rudd, K.E. et al. (2020) ‘Global, regional, and National Sepsis Incidence and mortality, 1990–2017: Analysis for the Global Burden of Disease Study’, The Lancet, 395(10219), pp. 200–211. doi:https:http://sci-hub.se/10.1016/s0140-6736(19)32989-7.

Seymour, C.W. et al. (2019) ‘Derivation, Validation, and Potential Treatment Implications of Novel Clinical Phenotypes for Sepsis’, JAMA, 321(20), pp. 2003–2017. doi:https:http://sci-hub.se/10.1001/jama.2019.5791.

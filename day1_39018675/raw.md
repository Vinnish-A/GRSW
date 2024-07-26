
Abstract
Background
Dysregulation of RNA guanine-7 methyltransferase (RNMT) plays a crucial role in the tumor progression and immune responses. However, the detailed role of RNMT in pan-cancer is still unknown.

Methods
Bulk transcriptomic data of pan-cancer were obtained from the Cancer Genome Atlas (TCGA), Genotype-Tissue Expression (GTEx), and Cancer Cell Line Encyclopedia (CCLE) databases. Single-cell transcriptomic and proteomics data of lung squamous cell carcinoma (LUSC) were analyzed in the Tumor Immune Single-cell Hub 2 (TISCH2) and Clinical Proteomic Tumor Analysis Consortium (CPTAC) databases, respectively. The correlation between RNMT expression and cancer prognosis was analyzed by Cox proportional hazards regression and Kaplan–Meier analyses. The correlation of RNMT expression with common immunoregulators, tumor mutation burden (TMB), microsatellite instability (MSI), mismatch repair (MMR), and DNA methyltransferase (DNMT) was analyzed. Additionally, the correlation between RNMT expression and immune infiltration level was evaluated. A total of 1287 machine learning combinations were used to construct prognostic models for LUSC. qRT-PCR and Western blot were used to validate the bioinformatics findings of RNMT upregulation in LUSC.

Results
RNMT was widely expressed across different cancers, with significant correlation to prognosis in cancers such as kidney chromophobe (KICH) (p = 0.0033, HR = 7.12), liver hepatocellular carcinoma (LIHC) (p = 0.01, HR = 1.41), and others. Notably, RNMT participates in the regulation of the tumor microenvironment. RNMT expression positively correlated with immune cell expression (Spearman’s rank correlation, p < 0.05). Moreover, RNMT expression was strongly associated with immunoregulators, TMB, MSI, MMR, and DNMT in most cancer types. Notably, RNMT expression displayed excellent prognostic and immunological performance in LUSC. The expression of RNMT was mainly enriched in B cells of LUSC tissues. qRT–PCR and Western blot verified the high expression of RNMT in LUSC.

Conclusion
RNMT expression widely correlated with prognosis and immune infiltration in various tumors, especially LUSC. The RNMT detection may provide a new idea for future tumor immune studies and treatment strategies.

1. Introduction
The prevalence of cancer has become a serious public health concern worldwide, with over 8 million deaths each year. The number of cancer patients will likely continue to increase over the coming decades (
Bray et al., 2013
, 
Tarver, 2012
). It is an intimidating and everlasting struggle to fight cancer. As the understanding of cancer diversity (
Hanahan, 2022
), the identification of powerful tumor markers offers hope for individual-based tumor diagnosis and treatment. Over the last few decades, modern immunotherapy has been regarded as a novel and promising direction for cancer treatment. Considerable progress has been made in immunotherapy, which has revolutionized tumor therapy in many ways. Currently, several immunotherapy strategies, such as monoclonal antibodies, adjuvants, and checkpoint inhibitors are available (
Rusch et al., 2018
). Immune checkpoints are a collection of inhibitory pathways intrinsic to the immune system. The expression of immune checkpoints is vital for maintaining self-tolerance and preventing autoimmunity (
Pardoll, 2012
). The rapid development of immune checkpoint blockade has made great help in practical clinical applications. For example, blocking the PD-1 and CTLA-4 pathways markedly increases the survival rate of patients with multiple malignancies, including melanoma, renal cell carcinoma, esophageal squamous cell carcinoma, and non-small cell lung cancer (
Larkin et al., 2019
, 
Albiges et al., 2020
, 
Doki et al., 2022
, 
Hellmann et al., 2019
). Clinical research on checkpoint inhibitors has become a research hotspot. Nonetheless, challenges still remained, including the translation of pre-clinical findings and the identification of the best therapy for individual patients (
Hegde and Chen, 2020
). Therefore, more clinical researches on potential and optimal targets need to be conducted in cancer immunotherapy.

N7-methylguanosine (m7G) is an electropositive modification of the mRNA 5′ cap structure, internal mRNA, rRNA, tRNA, miRNA, and lncRNA (
Malbec et al., 2019
, 
Pandolfini et al., 2019
, 
Wang et al., 2022
). m7G modification plays a significant role in mRNA export, metabolism, stability, splicing, and translation (
Zhang et al., 2019
). Recent research has indicated that changes in m7G affect the development and progression of cancer. Thus, m7G-related genes are considered promising biomarkers for prognosis and treatment (
Luo et al., 2022
). RNA guanine-7 methyltransferase (RNMT) contains an N-terminal regulatory domain. By regulating RNMT activity and recruitment, N-terminal regulatory domain can transcribe initiation sites (
Aregger and Cowling, 2013
, 
Glover-Cutter et al., 2008
). RNMT-mediated modification of m7G methylome plays an important role in RNA translation, the transformation from mammary epithelial cells to fibroblast cells, and T cell activation (
Cowling, 2010
, 
Galloway et al., 2021
). Previous studies have demonstrated that abnormal RNMT expression may accelerate the malignant growth of cancer. For example, the hypomethylated promoter of RNMT stimulates the progression of hepatocellular carcinoma tumorigenesis (
Stefanska et al., 2014
). Inhibition of RNMT induce the death of HeLa cells and breast cancer cells in a PIK3CA mutant background (
Chu and Shatkin, 2008
, 
Dunn et al., 2019
). Moreover, down-regulated RNMT expression inhibits the growth of glioma stem-like cells via the B7-H6/c-Myc axis (
Chen et al., 2020
). Although the function of RNMT in several cancers has been studied, its primary roles in tumor immunity are still unclear. With the rise of bioinformatics, multiple datasets can be used to predict the effects of numerous genes. Here, we obtained datasets from public databases. To evaluate the value of RNMT in pan-cancer, we analyzed survival prognosis, immune status, tumor mutation burden (TMB), microsatellite instability (MSI), mismatch repair (MMR) and DNA methyltransferase (DNMT). Quantitative real-time PCR (qRT–PCR) and Western blot were used to validate the accuracy of our study (
Shuqiang et al., 2022
).

3. Result
3.1. The expression level of RNMT in tissues
Based on CCLE database, we revealed the abnormal expression levels of RNMT in different cancers. Among the different cancer cell lines, RNMT was highly expressed in the salivary gland, skin, and stomach than in the other tissues, while the expression of RNMT in the kidney and breast was very low (
Fig. 1
A).

To analyze the differences in the expression of RNMT between normal and corresponding cancer tissues, the GTEx and TCGA databases were used. As shown in 
Fig. 1
B, RNMT expression was upregulated in 19 types of tumors compared to the normal samples, including GBMLGG, LGG, BRCA, ESCA, STES, KIRP, KIPAN, STAD, HNSC, KIRC, LUSC, LIHC, SKCM, PAAD, UCS, LAML, PCPG, ACC and CHOL. In contrast, RNMT was expressed at lower levels in GBM, COAD, PRAD, OV, COADREAD, and TGCT.

3.2. Prognostic value of RNMT in human pan-cancer
The TCGA dataset was utilized to assess the correlation between RNMT expression and prognosis in patients with different cancers. Cox proportional hazards regression model showed that RNMT expression impacted overall survival (OS) in 7 cancers, including KICH (p = 0.0033, HR = 7.12), LIHC (p = 0.01, HR = 1.41), ACC (p = 0.02, HR = 1.81), GBM (p = 0.05, HR = 1.38), GBMLGG (p < 0.0001, HR = 0.55), OV (p = 0.00085, HR = 0.83), THYM (p = 0.03, HR = 0.48), and SKCM (p = 0.05, HR = 0.84) (
Fig. 2
A). K–M curves revealed that high RNMT expression correlated with poor OS in LIHC (p = 0.00055), ACC (p = 0.0045), and KICH (p = 0.00052) patients, on the contrary, high RNMT expression correlated with good OS in GBMLGG (p < 0.0001), THYM (p = 0.01), and OV (p = 0.0082) patients (
Fig. 2
B-G).

However, it is possible that OS could be adversely affected by deaths other than cancer during follow-up. Thus, we reanalyzed the data to study the correlation between RNMT expression and the disease-free interval (DFI) among different tumor types. Cox proportional hazards regression model depicted the relationship in ACC (p = 0.0019, HR = 3.25), PRAD (p = 0.03, HR = 3.37), LUSC (p = 0.04, HR = 1.59), and OV (p = 0.02, HR = 0.74) (
Fig. 3
A). The K-M curves showed that high expression of RNMT correlated with poor DFI in PRAD (p = 0.01), LUSC (p = 0.0062), and ACC (p = 0.0031), while high RNMT expression correlated with good DFI in OV (p = 0.0071) (
Fig. 3
B-E).

3.3. Correlation of RNMT expression with tumor immune infiltration and tumor microenvironment in pan-cancer
Scoring the correlation of RNMT mRNA expression level with immune cell infiltration and tumor microenvironment aids in evaluating the prognosis and treatment sensitivity of different cancers (
Gajewski et al., 2013
). Using the TIMER database, we determined an association between RNMT expression and immune cell infiltration in different types of cancer. The level of RNMT mRNA expression had the strongest association with 3 types of tumors, namely, COAD, KIRC, and LIHC. Notably, RNMT expression was positively associated with the expression of immune cells (B cells, CD4+ T cells, CD8+ T cells, dendritic cells, macrophages, and neutrophils). More detailed information on RNMT expression and tumor immune infiltration is presented in 
Fig. 4
A.

According to the P value by analyzing of tumor microenvironment, 31 types of tumors were ranked. Only the top three tumors were presented here. As shown in 
Fig. 4
B, the stromal score was positively associated with RNMT expression in COAD (R = 0.27, p < 0.0001). The stromal scores of SARC (R = −0.333, p < 0.0001) and LUSC (R = −0.19, p < 0.0001) were negatively associated with the level of RNMT mRNA expression. The immune scores of SARC (R = −0.333, p < 0.0001), UCEC, (R = −0.131, p = 0.0022) and LUSC (R = −0.19, p < 0.0001) were negatively associated with the level of RNMT mRNA expression. Similar results were obtained for SARC (R = −0.333, p < 0.0001), LUSC (R = −0.19, p < 0.0001), and UCEC (R = −0.131, p = 0.0022) between the expression of RNMT and the estimated scores.

3.4. Correlation of RNMT expression with immunoregulators and immune checkpoints in pan-cancer
As shown in 
Supplementary Fig. S1
, RNMT expression positively correlated with immunoregulators in COADREAD, COAD, UVM, KIPAN, and PRAD. There were negative correlation between RNMT expression and immunoregulators in GBMLGG, SARC, LUSC, THCA, and LGG. Positive correlation of RNMT expression with the immunostimulators CD276, TNFRSF13C, and the immunoinhibitory TGFBR1 were also noted in most cancers. Due to immunotherapies are considerable treatments for tumor reduction and eradication, we investigated 24 immune inhibitors and 36 stimulators to explore the effect of RNMT on immune checkpoints. Our results showed that RNMT expression positively correlated with many immune checkpoints in most cancers, especially COAD, UVM, COADREA, PRAD, KIPAN, and LIHC. Negative associations between RNMT expression and immune checkpoints mainly existed in GBMLGG, SARC, TGCT, LGG, THCA, and LUSC. In addition, we revealed that RNMT expression was positively associated with immune checkpoints, including CD276, VEGFA, and HMGB1 in multiple cancers (
Fig. 5
). These results suggested that RNMT may modulate these immune checkpoints and strengthen immunity in some tumors.

3.5. Correlation of RNMT expression with TMB, MSI, DNA MMR genes, and DNMT
To better understand the role of RNMT, we evaluated the correlation of RNMT expression with TMB, MSI, DNA MMR genes, and DNMT. There was a significant positive association between the expression of RNMT and TMB in COAD, LAML, LUAD, SARC, SKCM, STAD, and THYM. A negative association between RNMT expression and TMB existed in BRCA, PRAD, and THCA patients (
Fig. 6
A). RNMT expression positively correlated with MSI in CESC, COAD, LUSC, SARC, STAD, TGCT, and UCEC patients. Besides, RNMT expression negatively correlated with MSI in DLBC, HNSC, PRAD, and THCA (
Fig. 6
B). The MMR genes included MLH1, MSH2, MSH6, PMS2, and EPCAM. Positive correlation of RNMT expression with MLH1, MSH2, MSH6, and PMS2 was revealed in most cancers, but not of RNMT expression with EPCAM (
Fig. 6
C). Moreover, RNMT expression levels were also significantly associated with DNMT1, DNMT2, DNMT3A, and DNMT3B in pan-cancer (
Fig. 6
D). In all, our results indicated that RNMT expression was immune-related and may impact the progression and prognosis of cancers.

3.6. Expression of RNMT in LUSC
RNMT displayed satisfactory prognostic and immunological performance in LUSC. Additionally, many key functional statuses including hypoxia, stemness, cell cycle, inflammation, and apoptosis correlated with RNMT expression in LUSC (
Fig. 7
A). We performed Bayesian network analysis. As shown in 
Supplementary Fig. S2
, RNMT expression directly impacted the functional statuses of stemness and apoptosis, while indirectly impacted the functional status of inflammation via the drug metabolism cytochrome p450 pathway. However, there was no the casual relationship of RNMT expression with hypoxia, and cell cycle. Consistent with our data analysis results of RNMT expression, RNMT mRNA expression in the tumor group was higher than that in the normal group (
Fig. 7
B). Similarly, Western blot and IHC results also showed that RNMT protein expression was higher in tumor group than the normal group (
Fig. 7
C-E). Furthermore, the expression of RNMT was higher in LUSC tissues than the normal group by analyzed the CPTAC database (
Fig. 7
F). Finally, significant differences in sex and weight were detected between LUSC and normal tissues (
Fig. 7
G-H).

3.7. Construction of machine learning models
To identify clinical factors that may affect the prognosis of LUSC patients, 1287 machine learning models were constructed (
Supplementary Table S1
). KNN+Lasso – CV: 5 fold (k = 1), KNN (k = 1), RF (mtry = 4, 50 %p), RF+Lasso – CV: 5 fold (mtry = 4, 50 % p), XGBoost – default, and XGBoost – default + Lasso – CV: 5 fold (cutoff: 0.5) were the best (AUC=1.000) models (
Fig. 8
A). RF (mtry = 4, 50 %p) and XGBoost – default) have the functions of ranking feature importance and filtering nonessential features. Thus, we observed the specific results of these two models. The results indicated that these covariates except for M stage were important for the outcome of LUSC patients (
Fig. 8
B-C). Notably, RNMT had the highest importance score, which further indicated that RNMT has potential as an excellent biomarker of LUSC.

3.8. ScRNA-seq analysis of RNMT in LUSC
The scRNA-seq data from the two GEO datasets were analyzed on the basis of the TISCH2 website (
Song et al., 2019
, 
Zilionis et al., 2019
). As shown in 
Fig. 9
, RNMT was expressed in immune cells, especially B cells in LUSC tissues. These results may imply that the dysregulation of RNMT expression in immune cells is associated with LUSC progression.

4. Discussion
Pan-cancer analysis can be used to investigate the similarities and differences among multiple cancer types. Furthermore, it is highly important because it offers novel insights and avenues for cancer prevention and treatment (
Schaub et al., 2018
). Recent research has extensively investigated the pan-cancer analysis of RNA alterations (
Consortium ITP, 2020
, 
Group PTC et al., 2020
, 
Rodriguez-Martin et al., 2020
). Pan-caner analysis contributes to uncovering mutations, driver genes, and the entire genome that play an important role in cancer development.

In order to explore the different expression of RNMT between normal tissues and tumors, we combined samples from TCGA and GTEx databases to analysis. Our results indicated decreased expression of RNMT in GBMLGG, which was consistent with previous studies (
Chen et al., 2020
). Similarly; decreased expression of RNMT was also found in BRCA. Dunn S et al. reported that RNMT inhibition contributed to reducing the proliferation of PIK3CA-mutant breast cancer cells (
Dunn et al., 2019
). These findings revealed that RNMT may play a specific role in specific tumor types. Exploring the function of RNMT might be an unexpected breakthrough via the incorporation of signaling pathways.

Next, we analyzed the relationship between RNMT mRNA expression and patient prognosis. According to the Cox proportional hazards model and K–M curves, patients with high RNMT expression in different cancer types, including LIHC, ACC, KICH, PRAD, and LUSC, had poor prognoses. In contrast, upregulated RNMT correlated with good prognosis in GBMLGG, THYM, and OV. These results proved that RNMT could represent a potential prognostic pan-cancer marker. 
Manning et al. (2020)
 reported that more RNA methyltransferases (RNMTs) were highly expressed in high-grade breast cancers. These studies demonstrated that RNMT probably play a considerable role in assessing the aggressiveness of cancers.

Tumor microenvironment has recently become a trending topic and has been extensively investigated in tumor therapy. Tumor cell development was closely related tumor microenvironment. In general, immune cells play an important role in antitumor effects. Extensive research indicated that immune cells in the complex tumor microenvironment may have a strong association with the occurrence and development of cancers (
Lianyuan et al., 2018
, 
Osipov et al., 2019
, 
Xu et al., 2018
, 
Chen et al., 2021
, 
Li et al., 2020
). Immune cells, such as T cells, B cells, and NK cells affect the aggressiveness and invasion degree of tumors (
Bejarano et al., 2021
). However, the pivotal correlation between RNMT expression and tumor microenvironment remains largely unknown. The results of our study showed that RNMT expression was positively related to various immune cell in several types of tumors. Therefore, RNMT is likely to be a promising new regulator to improve tumor microenvironment.

Immunomodulators are molecules that can enhance or inhibit immune function. For example, immunostimulators are predominantly used to improve antitumor effects and correct immune deficiency. Immune checkpoints are involved in a series of stimulation and inhibition pathways. Immune checkpoints can prevent uncontrolled immune responses and modulate self-tolerance. They are associated with dysfunctional T cells and have the ability to regulate T cells (
Locy et al., 2018
). In general, targeting immune checkpoints is a promising approach for tumor immunotherapy, as these checkpoints play a pivotal role in tumor immunosuppression. A previous study indicated that RNMT was closely related to the pathway of B7-H6/c-myc which plays an important role in activating NK cells (
Chen et al., 2020
). In this study, we conducted a systematic analysis and found that RNMT expression positively correlated with immune stimulators such as CD 276 and TNFRSF13C. In particular, RNMT was coexpressed with 24 immune inhibitors and 36 stimulators in cancers, specifically in UVM, COAD, COADREA, PRAD, KIPAN, and LIHC. The findings from our study highlighted the potential role of RNMT as a crucial modulator of cancer immunity. RNMT may orchestrate the recruitment and regulation of infiltrating immune cells to impede or facilitate cancer progression. Given that RNMT expression was notably relevant to the prognosis of UVM, COAD, COADREA, PRAD, KIPAN, and LIHC patients, our research can provide guidance for the development of immunotherapies in the future.

In this study, we found significant associations between RNMT and LUSC, including expression difference, prognosis, tumor microenvironment, immunoregulators, immune checkpoints, MSI, DNA MMR genes, and DNMT. Thus, we selected LUSC for further analysis. A recent study indicated that activation of RNMT promoted cellular G1 phase transcription, which further promoted cell proliferation (
Aregger et al., 2016
). In contrast, the percentage of apoptotic cells increased when RNMT activity decreased (
Dunn et al., 2019
). Similar to the above studies, our results showed that RNMT expression was positively associated with cell cycle and negatively correlated with apoptosis. Notably, no study has reported the correlation of RNMT expression with hypoxia, stemness, and inflammation in tumors, especially in LUSC. In our study, we first revealed positive correlation of RNMT expression with hypoxia, stemness, and negative correlation between RNMT expression and inflammation in LUSC. All of these factors may participate in the development of LUSC.

In the context of precision medicine, there is a growing realization that traditional clinical variable such as TNM stages may no longer fully satisfy the requirements of clinicians for optimal biomarkers (
Liu et al., 2022
). Previously, investigators primarily chose modeling algorithms based on their personal preferences and limited knowledge (
Liu et al., 2022
). To solve this problem, 1287 machine learning methods were used to construct prognostic signatures, and the results further confirmed that RNMT is an ideal biomarker.

Overall, our study revealed that RNMT differentially expressed in various cancers, which was associated with patient prognosis in different cancer types. Furthermore, carcinogenesis and tumor growth were related to the high RNMT expression. On this basis, our study elucidated the correlation of RNMT expression with tumor immune infiltration, tumor microenvironment, immunoregulators, MMR, DNA methylation, MSI, and TMB across diverse cancer types. These comprehensive analyses revealed the potential of RNMT as a promising therapeutic target and immunological biomarker in a wide range of cancers. Our analyses were based on public databases, and there was no adequate experimental validation. In the future, we will perform more functional experiments to further validate and expand upon our current findings. Although our research has several limitations, we have to acknowledge that RNMT is strongly associated with cancer development and tumor immunity in different cancer types.

5. Conclusions
RNMT widely correlated with prognosis and immune infiltration in various tumors, especially LUSC. RNMT may emerge as a promising potential biomarker for diagnosis and treatment of cancer.


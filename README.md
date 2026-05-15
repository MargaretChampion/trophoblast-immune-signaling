\# Trophoblast state and immune signaling at the maternal–fetal interface



\## Biological question



Do distinct trophoblast states associate with different immune-regulatory signaling environments at the maternal–fetal interface?



More specifically:

\- Are EVT, SCT, and VCT associated with distinct ligand programs?

\- Which decidual immune populations are positioned to receive those signals?

\- Do immune activation/tolerance states vary continuously within canonical immune subtypes?



\---



\## Dataset



Single-cell first-trimester maternal–fetal interface atlas from Vento-Tormo et al.



Primary cell populations analyzed:

\- Trophoblasts: EVT, SCT, VCT



\- Immune populations: decidual NK cells, T cells, decidual macrophages

Immune populations follow the original decidual immune annotations from the Vento-Tormo first-trimester placenta atlas.



Citations for all marker gene choices are at the bottom of this README.



\---



\## Analysis workflow



1\. Define trophoblast state structure

2\. Curate trophoblast immune-regulatory ligand programs

3\. Define immune receiver/receptor programs

4\. Score sender–receiver compatibility across cell populations

5\. Characterize immune functional-state structure

6\. Test associations between trophoblast state and immune signaling environments



\---



\# Trophoblast state analysis



Marker-based trophoblast state orientation across first-trimester placental trophoblast populations.



The following were used as trophoblast markers



| Trophoblast state | Core markers | Supportive markers | Notes                                                |

| ----------------- | ------------ | ------------------ | ---------------------------------------------------- |

| EVT               | HLA-G        | ITGA5, ERBB2       | Invasive extravillous trophoblast-associated program |

| SCT               | CGA, CGB     | LGALS16            | Syncytial/endocrine trophoblast program              |

| VCT               | KRT7, EGFR   | —                  | Villous epithelial/progenitor trophoblast state      |



Marker sets were used as state-orientation aids rather than absolute cell-type definitions, as trophoblast markers are often shared, transitional, or context-dependent across placental differentiation states.



!\[Trophoblast marker UMAPs](figures/trophoblast\_marker\_umaps.png)



Marker-based trophoblast state orientation. VCT was identified by KRT7 expression; EVT by HLA-G with ITGA5 and ERBB2 as supportive markers; SCT by CGA/CGB with LGALS16 as supportive. Supportive markers show overlapping but non-identical patterns, consistent with transitional and heterogeneous trophoblast states.



As a secondary check, I evaluated genes linked to characteristic trophoblast state programs and functional identities. Because VCT, EVT, and SCT occupy distinct biological roles within the placenta, we expect them to exhibit different expression patterns reflecting proliferation, invasion, immune interaction, and endocrine function.



VCT (villous cytotrophoblast) is a proliferative/progenitor epithelial trophoblast state, so we expect enrichment of epithelial and trophoblast maintenance programs.



EVT (extravillous trophoblast) is an invasive interface-engaging trophoblast lineage, so we expect enrichment of invasion, adhesion remodeling, and immune-regulatory programs.



SCT (syncytiotrophoblast) is a hormone-producing trophoblast layer, so we expect enrichment of endocrine and syncytialization-associated programs.



Marker genes:

\- \*\*HLA-G\*\* — immunomodulatory HLA molecule associated with EVT

\- \*\*CGA / CGB\*\* — subunits of human chorionic gonadotropin (hCG)

\- \*\*KRT7\*\* — broadly expressed trophoblast epithelial marker



!\[Trophoblast marker validation](figures/trophoblast\_marker\_violins.png)



The trophoblast annotations behave largely as expected.  

HLA-G expression is concentrated in EVT, consistent with an extravillous/interface-engaged trophoblast identity. CGA and CGB are enriched in SCT, consistent with syncytiotrophoblast endocrine and hCG-producing functions. KRT7 is broadly expressed across trophoblast populations, supporting its use as a pan-trophoblast epithelial marker rather than a state-specific marker.



Together, these expression patterns support the overall trophoblast state orientation and are consistent with expected trophoblast lineage biology.





Because trophoblast states exist along differentiation and functional continua, my downstream analyses emphasized broader biological programs rather than relying solely on discrete marker definitions. Using the Vento-Tormo atlas and recurrent trophoblast markers from first-trimester placental studies as a guide, I selected genes associated with the following programs:



The EVT/invasion program (HLA-G, ITGA1, MMP2, FN1, ASCL2) was designed to capture invasive and interface-engaged trophoblast biology. HLA-G is a canonical EVT-associated immunomodulatory molecule linked to maternal immune tolerance at the decidual interface. ITGA1, MMP2, and FN1 reflect extracellular matrix interaction and tissue remodeling processes frequently associated with trophoblast invasion, while ASCL2 has been linked to trophoblast lineage specification and invasive trophoblast states.



The SCT/syncytial program (CGA, CGB, SDC1, ERVFRD-1, LGALS16, GDF15) was designed to capture differentiated syncytiotrophoblast/endocrine biology. CGA and CGB encode subunits of hCG and are canonical syncytiotrophoblast markers. ERVFRD-1 (syncytin-2) is associated with trophoblast fusion, while SDC1, LGALS16, and GDF15 have been recurrently associated with placental endocrine and differentiated syncytial states.



The VCT/progenitor program (KRT7, TEAD4, TP63) was designed to capture broader trophoblast epithelial and progenitor-associated identity. KRT7 is commonly used as a pan-trophoblast epithelial marker, while TEAD4 and TP63 are associated with developmental and less differentiated trophoblast states.



!\[Trophoblast programs](figures/trophoblast\_programs\_violins.png)



These program scores support the interpretation that trophoblast populations occupy distinct but partially overlapping state spaces. EVT shows strong enrichment for an invasion/interface-engagement program, while SCT shows strong enrichment for a syncytial/endocrine program. VCT shows a broader progenitor-like profile, consistent with its role as a less differentiated villous trophoblast population. The partial overlap and heterogeneity are expected given that trophoblast identities exist along differentiation continua rather than as perfectly discrete transcriptional states.



\## Immune ligand program curation



To test whether trophoblast states differ in immune-regulatory signaling potential, I scored curated ligand-associated programs within trophoblast populations. Scores are interpreted as relative enrichment of ligand-associated transcriptional programs rather than direct evidence of ligand secretion or receptor engagement.



Programs were intentionally constrained and selected using maternal–fetal interface literature and trophoblast-focused immunology studies.



Complete program definitions, rationale, and supporting references are provided in:



`tables/immune\_ligand\_programs.xlsx`



!\[Immune Ligands](figures/trophoblast\_immune\_program\_umaps.png)



Projection of ligand-program scores onto the trophoblast UMAP reveals state-associated enrichment while preserving continuous variation across cells rather than collapsing populations into binary positive/negative groups. Nonclassical HLA/tolerance, checkpoint/inhibitory, and cytokine-conditioning programs are enriched along the EVT-associated region, while VCT and SCT remain comparatively lower. Importantly, these patterns preserve within-state heterogeneity and do not appear to be driven by isolated off-manifold cells, supporting their interpretation as continuous state-associated measures rather than strict categorical labels.



Having observed ligand-program gradients across the trophoblast UMAP, I next summarized these programs at the annotated trophoblast-state level. For each trophoblast sender state, I calculated the average score for each curated ligand program. This reduces the cell-level UMAP patterns into a compact sender-state profile that can be compared to receptor-program expression in immune receiver populations.

This step asks: which ligand programs are most enriched, on average, in VCT, EVT, and SCT?

!\[Ligand Program Enrichment](figures/trophoblast\_immune\_program\_umaps.png)


\## Key observations



\- EVT are strongly enriched for immune-regulatory ligand programs

\- Decidual NK populations show the strongest compatible receptor signatures

\- Immune functional states vary continuously within canonical immune subtypes

\- Trophoblast state better predicts tolerance-associated signaling than inflammatory signaling



\---



\## Planned extensions



\- Orthogonal ligand–receptor validation with CellPhoneDB

\- Integration of xenobiotic/stress-response programs

\- Cross-dataset projection into independent placenta atlases

\- Comparison against pathological pregnancy states











Citations for trophoblast markers:
Farah, O.; et al. Trophoblast lineage-specific differentiation and associated alterations in preeclampsia and fetal growth restriction. Int. J. Mol. Sci. 2020, 21, 4276.

Kaminker, J. D.; et al. Expression, Regulation, and Functions of the Galectin-16 Gene in Human Cells and Tissues. Biomolecules 2021, 11, 1930.

Haider, S.; et al. Transforming growth factor-β signaling governs the differentiation program of extravillous trophoblasts in the developing human placenta. Proc. Natl. Acad. Sci. U.S.A. 2022, 119, e2204780119.




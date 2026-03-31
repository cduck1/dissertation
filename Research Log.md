# Research Log

## Plan:
[X] 1. Acquire genome  
[X] 2. ANI Analysis  
[X] 3. Safety  
[X] 4. Genome stability  
[X] 5. Probiotic potential  
[ ] 6. Machine learning  

## **Acquire genome**
Action: Downloaded the complete genome assembly of Lactobacillus gigeriorum DSM 23908  
Source: NCBI RefSeq (ASM143657v1)  
Format: FASTA (.fna)  
Justification: RefSeq was chosen over GenBank (GCA) as it provides a curated, standardized version of the assembly, which is essential for high-quality downstream annotation.  

## **ANI Analysis**
Objective: To identify the similarity of this strain to phylogenetically closely-related species and species commonly used as probiotics.  
Tool: GTDB - skani ANI calculator  
Parameters: Minimum alignment fraction: 0, Screen < % identity: 1  

## **Safety**
Objective: To confirm this strain is considered safe - absence of resistance genes, virulence factors, and potential to produce biogenic amines.  
1. **Detection of acquired antibiotic resistance genes (ARGs) and chromosomal point mutations**  
   Tool: ResFinder 4.7.2 (web)  
   Database: ResFinder 2.5.1  
   Parameters: ID threshold 80%, minimum length 60%  
   Result: Zero hits  
   
2. **Detection of broad resistance including via antibiotic efflux and target alteration, and to biocides and heavy metals**  
   Tool: RGI (Resistance Gene Identifier) 6.0.5 (web)  
   Database: CARD (Comprehensive Antibiotic Resistance Database) 4.0.1  
   Parameters: Perfect and Strict hits only, excluded "Nudge" (hits ≥95% identity but initially categorized as Loose)  
   Result: Zero hits (Perfect:0, Strict:0, Loose:0)  
   
3. **Detection of virulence factors**  
   Tool: ABRicate 1.0.1 (via usegalaxy.org - web)  
   Database: VFDB (Virulence Factor Database) 2024-Dec-15  
   Parameters: Identity >= 80%, Coverage >= 80%  
   Result: Zero hits

4. **Detection of biogenic amine production**  
   Platform: Proksee  
   Tool: Bakta 1.8.2  
   Database: Bakta 5.0 (light)  
   Target Enzymes: Histidine, Tyrosine, Lysine, and Ornithine decarboxylases; Agmatine deiminase pathway  
   Target Enzymes Source: Biogenic Amine Production by Lactic Acid Bacteria: A Review (doi: 10.3390/foods8010017)  
   Result: Zero hits - identified from exporting the Bakta annotated genome to excel and searching for the target enzymes  

## **Genomic Stability**
Objective: To determine the stability of this strain from elements that can confer beneficial and dangerous genes.  
1. **Detection of IS (Insertion Sequence) elements, transposons, and plasmids**  
   Tool: MobileElementFinder 1.0.3  
   Database: MGEdb 1.0.2  
   Parameters: Minimum alignment coverage 95%, minimum sequence identity 90%, maximum truncation 30nt  
   Result: 1 of 23 mobile genetic elements found (ISL2)

2. **Detection of plasmids**  
   Tool: PlasmidFinder  
   Database: plasmidfinder_81c11f4_2023_12_04  
   Parameters: Minimal coverage: 0.6, minimal identity: 0.95  
   Result: Zero hits

3. **Detection of prophages**  
   Tool: PHASTER  
   Database: Bacteria DB last update: 22 Dec 2020, Prophage/Virus DB: 22 Dec 2020, DNA fragment DB of regions: 29 Mar 2018  
   Result: 4 prophage regions identified: 0 regions are intact, 1 region is incomplete, and 3 regions are questionable.  

4. **Detection of prophages**  
   Platform: Proksee  
   Tool: PHASTEST  
   Database: PHAST-BSD Bacterial Database – last updated in 22 Dec 2020  
   Result: 3 prophage regions identified: 2 regions are intact and 1 is questionable.

5. **Detection of genomic islands**  
   Tool: IslandViewer 4  
   Database: IslandPick, IslandPath-DIMOB, SIGI-HMM, and Islander
   Reference genome: Lactobacillus plantarum WCFS1  
   Result: 9 islands found

6. **Detection of CRISPR Cas sequences**  
   Tool: CRISPRCasFinder  
   Database: CRISPRCasdb  
   Result: 0 CRISPR sequences, 1 Cas cluster  

## **Probiotic Potential**
Objective: To determine this strain's probiotic potential.  
1. **Detection of genes associated with probiotic benefit**  
   Tool: NCBI tBLASTn
   Probiotic genes database: Supplementary Table S1 of Sabino, Y. N. V., Paiva, A. D., Fonseca, B. R., Medeiros, J. D., & Machado, A. B. F. (2025). Deciphering probiotic potential: a comprehensive guide to probiogenomic analyses. Future Microbiology, 20(7–9), 611–622. https://doi.org/10.1080/17460913.2025.2492472.  
   Parameters: >=40% percent identity, >=70% query coverage  
   Result: 71 matching records: Acid stress 6, Adhesion 5, Bile tolerance 9, Biosynthesis of vitamins 1, Cold stress 1, Exopolysaccharide biosynthesis 7, Gut persistence 1, Heat stress 1, Organic solvent stress 1, Osmotic stress 2, Oxidative stress 9, Starvation 2, Stress resistance 26  

2. **Detection of bacteriocins**  
   Tool: BAGEL4  
   Result: 2 bacteriocins identified  

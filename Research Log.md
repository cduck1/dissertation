# Research Log

## Plan:
[X] 1. Acquire genome  
[X] 2. Safety  
[ ] 3. Genome stability  
[ ] 4. Probiotic potential  

## **Acquire genome**
Action: Downloaded the complete genome assembly of Lactobacillus gigeriorum DSM 23908  
Source: NCBI RefSeq (ASM143657v1)  
Format: FASTA (.fna)  
Justification: RefSeq was chosen over GenBank (GCA) as it provides a curated, standardized version of the assembly, which is essential for high-quality downstream annotation.  

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

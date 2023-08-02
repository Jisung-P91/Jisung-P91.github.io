About
----

Hi, my name is Ji Sung Park. I am an organic chemist / medicinal chemist by training. 

I am interested in genome editing technologies as next-generation therapeutic modalities 

and as chemical biology tools to facilitate the discovery of traditional small molecule drugs. 

I have limited knowledge in this field, so I decided to commit to blogging 1 paper everyday

## **Blog #7 Base editor screens for in situ mutational scanning at scale - continued**
*2023-08-02*

I am still reading through this giant review paper which runs a comprehensive list of several mutational scanning approaches and compares them to the base editor scanning. The paper describes 5 ways to massively mutate a CDS of target protein to map its sequence-function landscape.

1. Base editor screen (will be covered tomorrow!)
2. CRISPR-Cas9 screens: 2/3 of the indels produced by Cas9 lead to the frameshift mutations. These mutations could lead to more deleterious outcomes for structural region of protein compared to flexible loop and thus its interpretation must be done carefully to account for possible biase in the screen readouts. Simiarly, the screen might find limited utility for screening the non-essential targets as the mutations would not affect the fitness outcomes of such targets. The advantage of this screen over base editor screening is that its large effect size might find the functional mutations in disordered proteins compared to base editor screen
3. PE screen: nCas9 (Cas9 H840A) nicks target strand, which allows the reverse-transcriptase to conjugate the nicked 5->3 strand off the RT template of the pegRNA. Its limitation in mutational screening is its variable editing efficiency and limited to small proteins possibly because its' editing window is 13 - 43 nt and pegRNA design is very challenging.
4. HDR screen (also known as saturation genome editing): similar to CRISPR-Cas9 screen + supplied with HDR template, which can introduce any mutations at the target gene. The limitation is its 100 nt window which necessitates multiple independent runs. Also, inevitably, to avoid subsequent cut by the Cas9, the template introduces a mutation in the PAM, which introduces the bystander mutations. 
5. Expression library screens : The customizable protein coding sequence is introduced as a libray. Virtually any mutation can be introduced throughout the whole protein, enabling the deep mutational scanning (DMS). However, the expression cassettes ignore the chromatin context and splicing. 

## **Blog #6 Base editor screens for in situ mutational scanning at scale**
*2023-07-31*

Disclaimer: I wanted to spend some time with my baby daughter, so took a little break.

The previous blog post was about using base editors for massively introducing the Stop codons. The base substitution at such large scale (3.4 mil sgSTOP to cover 97 - 99% of the genes) got me interested in the general overview of the base scanning tech. The general workflow of the base scanning goes like this:

<img width="1037" alt="Screenshot 2023-08-01 at 12 52 53 AM" src="https://github.com/Jisung-P91/Jisung-P91.github.io/assets/65584136/10b12116-d1bb-4e6c-91d6-b22d770eb121">

Figure adapted from Ref 1.

There are several ways to obtain the readouts on the consequences of base substitutions. One way is via directed evolution-style where the edited and fitted genes are directly sequenced. In this fashion, one would try to maximize the diversification of genetic variation. This can be achieved by using the targeted AID-mediated mutagensis and CRISPR X, which have very diffuse editing (CRISPR X has ~ 100-nt editing window).


Now in a more base editor scanning-stlye screen, one can measure the sgRNA abundance to determine if the base-subsituted gene was a loss-of-function/gain-of-function/neutral. In case the selected genes are not essential, a fluoresence reporter gene can be introduced and the function of target gene can be assessed by measuring the fluoresence output. 

<img width="769" alt="Screenshot 2023-08-01 at 1 15 28 AM" src="https://github.com/Jisung-P91/Jisung-P91.github.io/assets/65584136/9f832b14-ad8c-48c2-80c4-da6995ad1368">

Figure adapted from Ref 2.

Measurement of sgRNA abundance can be done at a single-cell level by single-cell RNA-seq. This approach allowed Sankaran's group to correlate the genes responsible for loss of function of transcription factor GATA1 to the erythroid differentiation as well as how the sgRNAs are represented in those different cell types after the differentiation.

<img width="424" alt="Screenshot 2023-08-01 at 1 25 58 AM" src="https://github.com/Jisung-P91/Jisung-P91.github.io/assets/65584136/fc694646-bb81-4c20-bcce-f9aaaf4d5548">

Figure adapted from the graphical abstrace of Ref 3. 

References.

    1. Lue, N. Z. & Liau, B. B. Base editor screens for in situ mutational scanning at scale. 
    Mol. Cell 83, 2167–2187 (2023).
    2. Lue, N. Z. et al. Base editor scanning charts the DNMT3A activity landscape. 
    Nat. Chem. Biol. 19, 176–186 (2023).
    3. Martin-Rufino, J. D. et al. Massively parallel base editing to map variant effects in human hematopoiesis. 
    Cell 186, 2456-2474.e24 (2023).
  


## **Blog #5 CRISPR-Mediated Base Editing Enables Efficient Disruption of Eukaryotic Genes through Induction of STOP Codons**
*2023-07-28*

CRISPR-Cas9 KO screening is a versatile tool that has been extensively used in various fields. Its mechanism relies on the DSB to induce the NHEJ or HR; the former could lead to adverse cellular effects via genome rearrangment and translocation, DNA damage checkpoint activation or cell death. The homology-directed repair is much cleaner mechanism but it is low efficient. Overall, such repair mechanisms lead to non-random outcomes (1).

Non-sense mutations for tumour suppressor genes are observed in 10 - 30 % of patients suffering from hereditary cancer syndromes such as familial breast and ovarian cancer. Moreover, pre-mature stoppage in the transcript can lead to non-sense mediated mRNA decay, which can lead to affecting other normal transcripts via DNA reaarangement (2). However, the problem is that there is no tool to study this. 

The base editor can convert the 4 codons, CAA/CAG/CGA and TGG into TAA/TAG/TGA. They then created a 3.4 mil sgSTOP, which is a sgRNA library to introduce the stop codons to 97 - 99% of genes. As a proof-of-concept, they transfected the HEK293 cells with the BE3 and with/without the sgSTOP targeting four genes. Then, if the target site was successfully replaced with the stop codon, the subsequent treatment with the restriction enzyme would not recognize it and thus no digestion would be observed. This assay, called restriction fragment length polymorphism (RFLP), was very useful.

<img width="413" alt="Screen Shot 2023-07-28 at 12 51 03 AM" src="https://github.com/Jisung-P91/Jisung-P91.github.io/assets/65584136/072255f4-3c08-4ae2-bb5d-482d6510e37b">

Figure adapted from Ref 1. 

Next, the authors wanted to see if they can create a KO cell line using the sgSTOP. As a result, they targeted the _SMARCAL1 _ AND _ATP1A1_; the latter would render the cells resistant to the ouabain treatment if its extracellular domain was mutated in the first loop and ultimately enriched the SMARCAL1-edited cells. As shown by the RFLP, the editing efficiency was increased when ouabain was added. To isolate the SMARCAL1 KO clones, the ouabain-resistant cell was seeded at a single cell density. About 10% of the clones was homozygously edited (1). 
    
<img width="643" alt="Screen Shot 2023-07-28 at 1 04 05 AM" src="https://github.com/Jisung-P91/Jisung-P91.github.io/assets/65584136/e194f4ae-ba97-48b4-b47f-fc0e6b2ff6b9">

Figure adapted from Ref 1. 

Moreover, the authors observed 1/11 of the modified clones with indels in the SMARCAL1 locus. Although the _ATP1A1_ could accumulate the indels, the authors believed that using the base editor would lower such chance. Base editors have very low indel rate (1.1% across six loci). This is because BE has the UGI to inhibit the uracil-N-glycosylase, which would otherwise excise the uracil, leaving the abasic site by the AP lyase and leading to the indel (3). Thus, the simultaneous indel accumulation at the _ATP1A1_ loci AND SMARCAL1 would be very rare. 

Now, can we use this screening at a genome scale? The STOP codon would be introduced at the 4 possible sites, which are 13 - 17 nucleotides away from the PAM site. About 62% of all 4 codons can be converted to the stop codons, which accounts to about 500K codons. This accounts for about 99.7% of the human genes can be targeted by this screening. 

Very cool work and its feasibility for genome-level screening makes it even more attractive tool for other researchers. To me, and I think it is briefly discusse din the paper, these stop codons can be effectively turned into amber codon (others maybe opal or ochre?) for multi-site labelling. I wonder if it can be paired with the prime editors.
  
References.

    1. van Overbeek, M. et al. DNA Repair Profiling Reveals Nonrandom Outcomes at Cas9-Mediated Breaks. 
    Mol Cell 63, 633–646 (2016)
    2. Lykke-Andersen, S. & Jensen, T. H. Nonsense-mediated mRNA decay: an intricate machinery that shapes transcriptomes. 
    Nat. Rev. Mol. Cell Biol. 16, 665–677 (2015).
    3. Rees, H. A. & Liu, D. R. Base editing: precision chemistry on the genome and transcriptome of living cells. 
    Nat. Rev. Genet. 19, 770–788 (2018).

## **Blog #4 dual stop codon suppression in mammalian cells with genomically integrated genetic code expansion machinery**

_2023-07-26_

Ref: https://www.biorxiv.org/content/10.1101/2023.03.26.534279v1

Building on the previous PiggyBac paper, Elsässer's group further matured their chemical biology tool to incorporate two stop codons in mammalian cells stably. They remained on the use of PB system and used the PylT/PylRS ochre suppressor and TyrT/AzFRS amber suppressor pairs and GFP^102TAG150TAA reporter integrated by PB transgenesis. As you see in the adapted figure from the original pre-print, Dual encoding of the suppressor rescues the expression of the modified GFP in HCT116 cells, which are apparently tough cell lines for GCE.  

<img width="808" alt="Screen Shot 2023-07-27 at 1 18 39 AM" src="https://github.com/Jisung-P91/Jisung-P91.github.io/assets/65584136/59de5dd7-4aba-4bc4-8fcb-3ad590a08ac7">

Figure adapted from the original pre-print. 

To their surprise, when they tested the same dual encoding system with the intracellular proteins such as tubulin and DAXX proteins, they found poor labelling intensity from the target proteins and very noisy background. The authors attributed this to unwanted mislabelling of C-terminal amber codons

<img width="546" alt="Screen Shot 2023-07-27 at 1 27 28 AM" src="https://github.com/Jisung-P91/Jisung-P91.github.io/assets/65584136/6f4fb70f-0e09-48f6-b407-aeb7eb1791f2"> <img width="278" alt="Screen Shot 2023-07-27 at 1 27 45 AM" src="https://github.com/Jisung-P91/Jisung-P91.github.io/assets/65584136/8028e266-70d1-4b76-a8ff-1a51574f6839">

Figure adapted from the original pre-print. 


## **Blog #3 Stable expression of unnaturral proteins in mammalian cells**

_2023-07-25_

    Ref: Elsässer, S. J., Ernst, R. J., Walker, O. S. & Chin, J. W. Nat. Methods 13, 158–164 (2016).

  Assignining causation to a biological perturbation is very complex. For example, to study the complex network of PTMs on histone, it is a no brainer to manipulate the PTM-inducing enzyme and then directly correlate the biological effect to this perturbation. However, it is known that such manipulation can have pleiotropic effects - lysine acetylation is one such example. Another approach is to use Cas9 as a recruiter to a target genetic loci, which is true but it is not site-specific (for example, if you want to modify a specific site of protein). 

  Transient expression of unnatural target protein via genetic code expansion gives hetergenous mixture of the target proteins, making it not reliable for causation-determining experiments. This approach is further confounded by variable level of transfection and ncAA incorporation due to variable read-through of the amber codon. 

  Chin group presented an alternate methodology where they packaged the engineered synthetase and tRNA along with unnatural protein of interest in a PiggyBac targeting vector. They also introduced the PiggyBac transposase to cut and paste these unnatural target genes into the host DNA. Brielfy, the vector contains multiple copies of PylT to ensure high efficiency and appended dendra for fluoresence-based sorting of the cells. If the ncAA is present, the cells should give out green fluoresence from dendra. Also, they introduced resistance markers (PuroR and NeoR) to select for cells with stably incorporated genes. 

<img width="864" alt="Screen Shot 2023-07-25 at 11 42 20 PM" src="https://github.com/Jisung-P91/Jisung-P91.github.io/assets/65584136/f9abdff1-e494-4241-ab16-c79683f4272e">

Figure adapted from Elsässer, S. J., Ernst, R. J., Walker, O. S. & Chin, J. W. Nat. Methods 13, 158–164 (2016)

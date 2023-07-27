Hi, my name is Ji Sung Park. I am an organic chemist / medicinal chemist by training. 

I am interested in genome editing technologies as next-generation therapeutic modalities 

and as chemical biology tools to facilitate the discovery of traditional small molecule drugs. 

I have limited knowledge in this field, so I decided to commit to blogging 1 paper everyday.

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

# Project 1: From DNA to Protein - Sequence Analysis Fundamentals

## Objective
To establish a foundational understanding of the central dogma of molecular biology by building a Python tool that translates a DNA sequence into a protein sequence and performs basic bioinformatic analysis.

## Biological Background
 
 
###  Genetic Building Blocks

These are the fundamental monomers (individual units) that make up nucleic acids (DNA/RNA) and proteins.

| Molecule Type | Components | Key Role | Notes |
| :--- | :--- | :--- | :--- |
| **DNA Nucleotides** | Adenine (**A**), Thymine (**T**), Cytosine (**C**), Guanine (**G**) | Long-term genetic storage (The Blueprint) | Forms the stable **double helix** structure. A pairs with T; C pairs with G. |
| **RNA Nucleotides** | Adenine (**A**), **Uracil (U)**, Cytosine (**C**), Guanine (**G**) | Messenger and functional molecule | **T becomes U** in RNA. Typically **single-stranded**. |
| **Amino Acids** | **20** standard types | Building blocks of **proteins** | The sequence dictates the protein's final 3D structure and function. |

---

### The Genetic Code

The set of rules for translating the nucleotide sequence into an amino acid sequence.

* **Codon:** A sequence of **three consecutive nucleotides** on the mRNA. Each codon specifies either a single amino acid or a regulatory signal (start/stop).
    * There are $4^3 = 64$ possible unique codons.
* **Start Codon:** **AUG**
    * **Function 1:** Codes for the amino acid **Methionine (Met)**.
    * **Function 2:** Signals the **beginning** of translation.
* **Stop Codons:** **UAA**, **UAG**, **UGA**
    * **Function:** Signals the **termination** (end) of translation. They do not code for any amino acid.

---

### Key Rules for Translation (The Central Dogma)

 
The central dogma describes the fundamental flow of genetic information within a biological system:

$$\text{DNA} \xrightarrow{\text{Transcription}} \text{mRNA} \xrightarrow{\text{Translation}} \text{Protein}$$

* **Transcription:** The process where a DNA template is copied into messenger RNA (**mRNA**). Biologically, the nucleotide **Thymine (T)** in DNA is replaced by **Uracil (U)** in RNA. Biopython handles this substitution with a single method call.
* **Translation:** The mRNA sequence is decoded in triplets (**codons**) by the ribosome. Each codon specifies a particular amino acid, building the final chain known as a **protein**.


The process of converting DNA information into functional proteins.

### 1. Transcription (DNA to RNA)
* **Process:** An RNA molecule is synthesized from a DNA template.
* **Key Rule:** **Replace all T's with U's.**
    * If the DNA template sequence is `...TAG...`, the resulting mRNA sequence will be `...AUC...`.

### 2. Reading Frame
* **Process:** The mRNA sequence must be correctly divided into triplets.
* **Key Rule:** **Read sequence in groups of 3 starting from the first nucleotide (AUG).**
    * An incorrect start position results in a **frameshift mutation**, changing every subsequent codon.
    * *Example (Correct Frame):* `AUG | UCA | GGU...` $\rightarrow$ Met - Ser - Gly...
    * *Example (Shifted Frame):* `A | UGU | CAG | GU...` $\rightarrow$ Cys - Gln... (Incorrect protein)

### 3. Translation (RNA to Protein)
* **Process:** Ribosomes read the mRNA codons and recruit corresponding tRNA molecules, which carry specific amino acids.
* **Key Rule:** **Use codon table to map 3-letter codes to amino acids.**

### 4. Termination
* **Process:** The finished protein chain is released from the ribosome.
* **Key Rule:** **Stop when reaching a stop codon (UAA, UAG, or UGA).**


---

## Codon Table

A codon table is a chart used to translate the genetic code, showing which sequence of three nucleotide bases (a codon) corresponds to a specific amino acid during protein synthesis.

It is the fundamental key for understanding how the linear information stored in DNA/RNA is converted into the functional components of a cell: proteins


- **Codon**: A sequence of three adjacent nucleotides (a triplet) in an mRNA molecule.3 Since there are four possible nucleotides (Adenine, Uracil, Cytosine, Guanine—A, U, C, G) in RNA, there are $4^3 = 64$ possible codons.

- **Translation**: This is the biological process where the ribosome reads the mRNA sequence, using the codon table to link the appropriate amino acids together to form a polypeptide chain (protein).



#### Standard Codon Table Structure
The standard codon table is typically represented using mRNA codons (which contain Uracil, U, instead of the Thymine, T, found in DNA), and is arranged to be easily readable:

**First Base**: Located along the left vertical axis (e.g., U, C, A, or G).

**Second Base**: Located along the top horizontal axis (e.g., U, C, A, or G).

**Third Base**: Located along the right vertical axis within a specific box defined by the first two bases.

By finding the intersection of the first and second bases, and then locating the third base, you can determine the specific amino acid or signal.


#### Special Codons
Of the 64 possible codons, 61 code for the 20 common amino acids, and the remaining 3 are signals:

**Start Codon**: AUG (codes for the amino acid Methionine, Met). This codon usually signals the start of translation and the beginning of a polypeptide chain.

**Stop Codons**: UAA, UAG, and UGA. These codons do not code for an amino acid; instead, they signal the ribosome to stop translation and release the completed polypeptide chain.



## Datasets & Resources
- **Data:**  
Data was downloaded from Genecode
[Human Protein-coding transcript sequences](https://ftp.ebi.ac.uk/pub/databases/gencode/Gencode_human/release_49/gencode.v49.pc_transcripts.fa.gz)
 
- **Tools:** Biopython for sequence manipulation (`!pip install biopython`)



---

REFERENCES: 

- [Biopython Tutorial & Cookbook](https://biopython.org/docs/dev/Tutorial/index.html)
 


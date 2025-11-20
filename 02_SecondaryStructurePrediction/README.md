#   Protein Secondary Structure Prediction

This chapter focuses on predicting a protein's local structural conformation from its amino acid sequence. It serves as an excellent introduction to applying machine learning techniques to complex biological sequence analysis.

---

## Essential Theory Notes

### What is Secondary Structure?

Secondary structure refers to the **local folding patterns** within a polypeptide chain. These patterns are stabilized primarily by **hydrogen bonds** between the backbone atoms (the carboxyl oxygen and the amide hydrogen) of the amino acids. Understanding these patterns is the crucial intermediate step between the primary structure (amino acid sequence) and the final tertiary structure (3D fold).

#### 1. Alpha-Helix (H)
* **Structure:** A **spiral, rod-like** conformation. 
* **Stabilization:** Formed by $\text{H-bonds}$ between the **$C=O$ group** of residue $n$ and the **$N-H$ group** of residue $n+4$. This $i \to i+4$ bonding pattern results in 3.6 residues per turn.
* **Properties:** Side chains project outward, minimizing steric hindrance.

#### 2. Beta-Sheet (E)
* **Structure:** An **extended, pleated** conformation formed by two or more $\beta$-strands lying adjacent to each other. 
* **Stabilization:** $\text{H-bonds}$ form **laterally** between the backbone atoms of adjacent strands.
    * **Parallel:** Strands run in the same N-to-C direction. $\text{H-bonds}$ are slanted.
    * **Antiparallel:** Strands run in opposite N-to-C directions. $\text{H-bonds}$ are perpendicular to the strands and stronger.
* **Properties:** Can be an extensive, rigid structure central to many protein folds.

#### 3. Coil (C)
* **Structure:** This is a catch-all category for **everything else** that is not a stable $\alpha$-helix or $\beta$-sheet.
* **Components:** Includes loops, turns (like the $\beta$-turn which reverses the chain direction), and segments referred to as "random coils."
* **Properties:** Generally more flexible and solvent-exposed; often found on the protein's surface.



### What is SS distribution?

SS distribution means:

“How many residues are helix, sheet, or coil?"
  
  - ( residue => an individual amino acid within a polypeptide chain)

SS distribution is a summary or histogram of the protein’s secondary structure composition.



### What are PDB Files?

PDB stands for Protein Data Bank, and a PDB file is a text file format that describes the 3D structure of a protein, DNA, RNA, or complex.

PDB Files contain atomic coordinates (x, y, z) for each atom in the molecule.

PDB file describes:

- Chains (A, B, …)
- Residues (amino acids or nucleotides)
- Atom types (Cα, N, O, side chains, ligands)
- Optional data: secondary structure, crystallography info, experimental resolution, heteroatoms, etc.


PDB files are  written with `.pdb` or `.ent` extensions.

Historically, the Protein Data Bank distributed files as `.ent` (for “entry”).
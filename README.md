# Workflow Metagenomik

## About

Workflow_Metagenomik adalah repository yang berisi tahapan analisis bioinformatika untuk identifikasi dan analisis filogenetik bakteri berdasarkan gen 16S rRNA. Workflow ini mencakup pengambilan data sekuens, multiple sequence alignment, konstruksi pohon filogenetik, serta visualisasi hasil menggunakan perangkat lunak bioinformatika yang umum digunakan.

Repository ini dibuat untuk mendukung pembelajaran dan penelitian di bidang mikrobiologi, biologi molekuler, dan bioinformatika.

---

## Complete Workflow Documentation

Dokumentasi lengkap workflow dapat ditemukan pada setiap notebook dan script yang tersedia dalam repository ini.

---

## Current Analysis

Analisis dilakukan terhadap enam spesies bakteri laut berdasarkan sekuens gen 16S rRNA:

* Chromohalobacter salexigens
* Marinobacter nauticus
* Flavobacterium beibuense
* Halopseudomonas aestusnigri
* Pseudomonas mendocina
* Pseudoalteromonas lipolytica

---

## Quick Start

### Clone Repository

```bash
git clone https://github.com/USERNAME/Workflow_Metagenomik.git
cd Workflow_Metagenomik
```

### Install Dependencies

```bash
pip install biopython matplotlib
```

### Run Phylogenetic Analysis

```bash
python phylogenetic_analysis.py
```

---

## Workflow Overview

Workflow yang digunakan dalam penelitian ini meliputi:

1. Pengambilan sekuens gen 16S rRNA dari NCBI GenBank.
2. Quality checking data sekuens.
3. Multiple Sequence Alignment menggunakan Clustal Omega.
4. Import hasil alignment ke MEGA 11.
5. Konstruksi pohon filogenetik menggunakan metode Neighbor-Joining.
6. Evaluasi hubungan kekerabatan berdasarkan nilai bootstrap.
7. Visualisasi dan interpretasi hasil.

---

## Repository Structure

```text
Workflow_Metagenomik/
│
├── data/
│   ├── sequences.fasta
│   └── alignment.fasta
│
├── scripts/
│   └── phylogenetic_analysis.py
│
├── results/
│   ├── phylogenetic_tree.png
│   ├── phylogenetic_tree.nwk
│   └── distance_matrix.csv
│
├── notebooks/
│   └── phylogenetic_analysis.ipynb
│
└── README.md
```

---

## Software Used

* Clustal Omega
* MEGA 11
* Python
* Biopython
* Matplotlib
* NCBI GenBank

---

## Example Commands

### Multiple Sequence Alignment

```bash
clustalo -i sequences.fasta -o alignment.fasta --force
```

### Generate Phylogenetic Tree

```bash
python phylogenetic_analysis.py
```

---

## Output Files

| File                  | Description                 |
| --------------------- | --------------------------- |
| alignment.fasta       | Multiple sequence alignment |
| phylogenetic_tree.nwk | Tree in Newick format       |
| phylogenetic_tree.png | Tree visualization          |
| distance_matrix.csv   | Genetic distance matrix     |

---

## Phylogenetic Tree

Tambahkan hasil pohon filogenetik pada bagian ini.

```markdown
![Phylogenetic Tree](results/Screenshot 2026-06-10 110308.png)
```

---

## Citation

Jika menggunakan workflow ini dalam penelitian atau tugas akademik, mohon mencantumkan sitasi yang sesuai untuk perangkat lunak yang digunakan:

* Kumar et al. (2021). MEGA11: Molecular Evolutionary Genetics Analysis Version 11.
* Sievers & Higgins (2018). Clustal Omega.
* NCBI GenBank Database.

---

## Author

Nayla Faiha

Program Studi Ilmu Kelautan

Universitas Padjadjaran

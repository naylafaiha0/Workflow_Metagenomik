pip install biopython matplotlib
from Bio import AlignIO
from Bio.Phylo.TreeConstruction import DistanceCalculator
from Bio.Phylo.TreeConstruction import DistanceTreeConstructor
from Bio import Phylo
import matplotlib.pyplot as plt

# ==========================
# INPUT FILE ALIGNMENT FASTA
# ==========================
alignment_file = "alignment.fasta"

# Membaca alignment
alignment = AlignIO.read(alignment_file, "fasta")

print("Jumlah sekuens :", len(alignment))
print("Panjang alignment :", alignment.get_alignment_length())

# ==========================
# HITUNG JARAK GENETIK
# ==========================
calculator = DistanceCalculator('identity')
distance_matrix = calculator.get_distance(alignment)

print("\nDistance Matrix:")
print(distance_matrix)

# ==========================
# MEMBANGUN POHON NJ
# ==========================
constructor = DistanceTreeConstructor()
tree = constructor.nj(distance_matrix)

# ==========================
# SIMPAN POHON
# ==========================
Phylo.write(tree, "phylogenetic_tree.nwk", "newick")

print("\nPohon berhasil disimpan:")
print("phylogenetic_tree.nwk")

# ==========================
# VISUALISASI POHON
# ==========================

from Bio.Align.Applications import ClustalOmegaCommandline

clustalomega_cline = ClustalOmegaCommandline(
    infile="sequences.fasta",
    outfile="alignment.fasta",
    verbose=True,
    auto=True
)

clustalomega_cline()

plt.figure(figsize=(12,8))
Phylo.draw(tree, do_show=False)
plt.savefig("Screenshot 2026-06-10 110308.png", dpi=300, bbox_inches="tight")
plt.close()

print("Gambar pohon tersimpan sebagai phylogenetic_tree.png")
plt.figure(figsize=(12, 8))
Phylo.draw(tree)
plt.show()

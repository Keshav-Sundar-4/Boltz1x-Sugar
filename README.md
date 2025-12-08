# Boltz1x-Sugar
A novel addition to the base Boltz model that allows for improved Glycoprotein, Glycan, and Lectin-Glycan structure prediction


## Training Pipeline Modifications/Improvements
- Added raw PDB and MD trajectory file cleaning to ensure preprocessing compatability
- Due to issues with CIF file generation, the entire Boltz preprocessing script was refactored for PDB file compatability
- Introduced novel glycan pseudo-polymer tokenization and trained on inter-residue bonds (Currently missing from Boltz - Inter-residue bonding is handled through inference-time potentials). Added anomeric bond constraints to the model
- Introduced a inter-glycan focused minipairformer for accurate modeling of glycan biophysics
- Introduced a new two-part training paradigm to ensure preservation of trained interaction biophysics whilst maximizing MD simulation glycan conformation data
- Modified cropping logic to adhere with a glycan-focused dataset
- Refactored yaml parsing to allow for IUPAC --> structure prediction rather than relying on SMILES (Particularly for dealing with larger oligosaccharides)
- Tuned hyperparams for optimal glycan taining


## Benchmarks (To be updated):

### Pre-Training (SMILES)
DockQC:   	 0.181

### Post-Training (IUPAC)
DockQC:   	 0.281

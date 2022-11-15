### Reprotox Knowledge Graph Serializations
| Name                          | Size        | Date Updated | Nodes           |  Edges          | Link | Remarks |
| :---------------------------- | :---------- | :----------- | :-------------- | :-------------- | :--- | :------ |
| drug_and_gene_birth-defects-associations_serialization        | 1.6MB       | 11/15/2022   | 1433            | 2252            | [link](https://s3.amazonaws.com/maayan-kg/reprotox/reprotox_serialization.valid.json) | Associations from [DrugShot](https://maayanlab.cloud/drugshot/), [DrugEnrichr](https://maayanlab.cloud/DrugEnrichr/), and [GeneShot](https://maayanlab.cloud/GeneShot/) |
| drug_and_gene_associations_from_lincs_serialization    | 114.6MB      | 11/15/2022 | 8942 | 225509 | [link](https://s3.amazonaws.com/maayan-kg/reprotox/sigcom_lincs_serialization.valid.json) | Top up- and down- regulated genes from [LINCS](https://lincsproject.org/) L1000 chemical perturbation signatures |
| drug_and_drug_similarity_from_lincs_serialization    | 15MB      | 11/15/2022 | 4523 | 20785 | [link](https://s3.amazonaws.com/maayan-kg/reprotox/sigcom_lincs_drug_similarity.valid.json) | Top up- and down- regulated genes from [LINCS](https://lincsproject.org/) L1000 chemical perturbation signatures |
| drug_and_birth-defects_associations_from_FAERS_male_serialization            | 205KB       | 11/15/2022 | 117  | 179   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/drugsto_faers_male.valid.json) | Drug/Birth Defect associations extracted from the FAERS database by IDG |
| drug_and_birth-defects_associations_from_FAERS_female_serialization          | 211KB       | 11/15/2022 | 126  | 193   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/drugsto_faers_female.valid.json) | Drug/Birth Defect associations extracted from the FAERS database by IDG |
| HPO_associated_genes          | 50.8MB       | 11/15/2022 | 5152  | 125458   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/hpo.valid.json) | Birth defect associated genes taken from [HPO](https://hpo.jax.org/) |
| ARCHS4_coexpression_associations          | 93.8MB       | 11/15/2022 | 17964  | 170801   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/archs4_coexpression.valid.json) | Co-expression association from [ARCHS4](https://maayanlab.cloud/archs4) |
| drug_and_HPO-associations_serialization        | 8.9MB       | 11/15/2022   | 2802            | 12502            | [link](https://s3.amazonaws.com/maayan-kg/reprotox/Drugshot_HPO_to_Drug.valid.json) | Associations from [DrugShot](https://maayanlab.cloud/drugshot/) using [HPO](https://hpo.jax.org/) terms |
| gene_and_HPO-associations_serialization        | 7.2MB       | 11/15/2022   | 6064            | 13487            | [link](https://s3.amazonaws.com/maayan-kg/reprotox/Geneshot_HPO_to_Gene.valid.json) | Associations from [GeneShot](https://maayanlab.cloud/geneshot/) using [HPO](https://hpo.jax.org/) terms |
| idg_drug_targets-associations_serialization        | 6.4MB       | 11/15/2022   | 2395            | 7326            | [link](https://s3.amazonaws.com/maayan-kg/reprotox/idg_drug_targets.valid.json) | Drug targets from IDG|


### Ingesting data to a neo4j instance

A script for ingesting the above serializations are provided [here](https://raw.githubusercontent.com/MaayanLab/reprotox-kg/main/scripts/populate.py).

#### Running the populate script:
1. Download the script from [here](https://raw.githubusercontent.com/MaayanLab/reprotox-kg/main/scripts/populate.py).
2. Download `requirements.txt` from [here](https://raw.githubusercontent.com/MaayanLab/reprotox-kg/main/scripts/download.md).
3. `pip install requirements.txt`
4. Create a `.env` file and edit the following variables:
   ```
    # .env
    NEO4J_URL=neo4j://localhost:7687
    NEO4J_USER=neo4j
    NEO4J_NAME=reprotox
    NEO4J_PASSWORD=mysecretpassword
   ```
5. run `python populate.py --dir <directory> --merge=y`

### Additional files

| Name                          | Size        | Date Updated | link                                                                          |
| :---------------------------- | :---------- | :----------- | :---------------------------------------------------------------------------  |
| Gene Susceptibility Scores    | 1.1 MB      | 07-27-2022   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/susceptibility_scores.csv) |
| Placental Crossing and D & X Category Predictions      | 3.8 MB      | 09-12-2022   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/L1000_2021_Signature_Similarity_predicted_drug_table.tsv) |
| HPO Frequency                 | 1.1 MB      | 07-27-2022   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/HPO_Freq.tsv) |
| CNS Phenotypes                | 8 KB      | 08-02-2022   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/CNS%20Phenotypes.csv) |
| Great Vessels Phenotypes                | 8 KB      | 08-02-2022   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/Great%20Vessels%20Phenotypes.csv) |
| Heart Phenotypes                | 8 KB      | 08-02-2022   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/Heart%20Phenotypes.csv) |
| ReproTox KG Cycles              | 20 KB     | 09-12-2022   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/ReproTox_KG_Cycles.tsv) |
| ReproTox KG Cycles with Expanded HPO Term              | 432 KB     | 09-12-2022   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/ReproTox_KG_Cycles_with_Expanded_HPO_Term.tsv) |
| ReproTox Phenotype Anatomy              | 37 KB     | 09-13-2022   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/ReproTox_Phenotype_Anatomy.tsv) |
| ReproTox KG topology measures              | 50 KB     | 09-15-2022   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/ReproTox-KG-Topology-Measures-09152022.pdf) |

### Reprotox Knowledge Graph Serializations
| Name                          | Size        | Date Updated | Nodes           |  Edges          | Link | Remarks |
| :---------------------------- | :---------- | :----------- | :-------------- | :-------------- | :--- | :------ |
| drug_and_gene_birth-defects-associations_serialization        | 1.1MB       | 07/27/2022   | 1427            | 2252            | [link](https://s3.amazonaws.com/maayan-kg/reprotox/reprotox_serialization.valid.json) | Associations from [DrugShot](https://maayanlab.cloud/drugshot/), [DrugEnrichr](https://maayanlab.cloud/DrugEnrichr/), and [GeneShot](https://maayanlab.cloud/GeneShot/) |
| drug_and_gene_associations_from_lincs_serialization    | 89.4MB      | 07/27/2022 | 8943 | 225523 | [link](https://s3.amazonaws.com/maayan-kg/reprotox/sigcom_lincs_serialization.valid.json) | Top up- and down- regulated genes from [LINCS](https://maayanlab.cloud/sigcom-lincs/) L1000 chemical perturbation signatures |
| drug_and_drug_similarity_from_lincs_serialization    | 8.2MB      | 07/27/2022 | 4523 | 20785 | [link](https://s3.amazonaws.com/maayan-kg/reprotox/sigcom_lincs_drug_similarity.valid.json) | Top up- and down- regulated genes from [LINCS](https://maayanlab.cloud/sigcom-lincs/) L1000 chemical perturbation signatures |
| drug_and_birth-defects_associations_from_FAERS_male_serialization            | 103KB       | 07/12/2022 | 117  | 179   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/drugsto_faers_male.valid.json) | Drug/Birth Defect associations extracted from the FAERS database by IDG |
| drug_and_birth-defects_associations_from_FAERS_female_serialization          | 111KB       | 07/12/2022 | 126  | 193   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/drugsto_faers_female.valid.json) | Drug/Birth Defect associations extracted from the FAERS database by IDG |
| HPO_associated_genes          | 38MB       | 07/28/2022 | 5195  | 126862   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/hpo.valid.json) | Birth defect associated genes taken from HPO |

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

### Miscellaneous files

| Name                          | Size        | Date Updated | link                                                                          |
| :---------------------------- | :---------- | :----------- | :---------------------------------------------------------------------------  |
| Gene Susceptibility scores    | 1.1 MB      | 07-27-2022   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/susceptibility_scores.csv) |
| Placenta Crossing scores      | 866 KB      | 07-27-2022   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/L1000_2021_Signature_Similarity_predicted_drug_table.csv) |
| HPO Frequency                 | 1.1 MB      | 07-27-2022   | [link](https://s3.amazonaws.com/maayan-kg/reprotox/HPO_Freq.tsv) |
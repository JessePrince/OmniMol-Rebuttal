# OmniMol-Rebuttal
## 1 Supplementary Result for gradient conflict
| Source Task         | Target Task              | Similarity  | Degree |
|---------------------|--------------------------|-------------|--------|
| forward             | molcap                   | 0.00106     | 89.97  |
| forward             | homolumo                 | 0.00412     | 89.97  |
| forward             | experiment               | -0.07568    | 94.45  |
| forward             | scf                      | -0.08154    | 94.90  |
| forward             | scf&exp                  | -0.08057    | 94.45  |
| forward             | scf&logp                 | -0.03882    | 92.21  |
| forward             | homo&yield&logp&tpsa     | -0.00372    | 90.42  |
| molcap              | homolumo                 | -0.00903    | 90.42  |
| molcap              | experiment               | -0.11475    | 96.69  |
| molcap              | scf                      | -0.01208    | 90.87  |
| molcap              | scf&exp                  | -0.04688    | 92.66  |
| molcap              | scf&logp                 | -0.05591    | 93.11  |
| molcap              | homo&yield&logp&tpsa     | -0.07764    | 94.45  |
| homolumo            | experiment               | 0.09766     | 84.60  |
| homolumo            | scf                      | 0.10400     | 84.15  |
| homolumo            | scf&exp                  | 0.09180     | 84.60  |
| homolumo            | scf&logp                 | 0.08252     | 85.05  |
| homolumo            | homo&yield&logp&tpsa     | 0.03320     | 88.18  |
| experiment          | scf                      | -0.02991    | 91.76  |
| experiment          | scf&exp                  | 0.37891     | 67.59  |
| experiment          | scf&logp                 | 0.04932     | 87.29  |
| experiment          | homo&yield&logp&tpsa     | 0.04639     | 87.29  |
| scf                 | scf&exp                  | 0.20020     | 78.33  |
| scf                 | scf&logp                 | 0.56250     | 55.73  |
| scf                 | homo&yield&logp&tpsa     | 0.19434     | 78.78  |
| scf&exp             | scf&logp                 | 0.21680     | 77.44  |
| scf&exp             | homo&yield&logp&tpsa     | 0.09668     | 84.60  |
| scf&logp            | homo&yield&logp&tpsa     | 0.39063     | 67.14  |

Table 1: The complete results of cosine similarity of gradient weight in attention layers, we measured on the following tasks



## 2 

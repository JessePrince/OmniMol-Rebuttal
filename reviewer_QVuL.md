## Section 1: Supplementary evidence for conflicting gradient

> We examine the gradients for each individual task as well as for various combinations of tasks, and compute the cosine similarity between each pair of gradient vectors, focusing particularly on the average weights of the attention and feed-forward layers. By analyzing the angles derived from the cosine similarities, we observe that the directions of these gradients diverge and fail to form a cohesive force. As shown in Table 1, this large angular separation clearly indicates that the gradient directions of most tasks are in conflict when learned jointly. This analysis is also in accordance with the idea of solving the challenging multi-task learning, which is a good example to support our motivation.

**Table 1: The complete results of cosine similarity of gradient weight in attention layers.**
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

**Table 2: The complete results of cosine similarity of gradient weight in feed-forward layers.**

| Source Task               | Target Task                | Similarity | Degree |
|--------------------------|----------------------------|------------|--------|
| forward                  | molcap                     | 0.04248    | 87.73  |
|                          | homolumo                   | 0.10400    | 84.15  |
|                          | experiment                 | -0.00705   | 90.42  |
|                          | scf                        | 0.03418    | 88.18  |
|                          | exp&scf                    | 0.00668    | 89.52  |
|                          | scf&logp                   | 0.05151    | 86.84  |
|                          | homo&yield&logp&tpsa       | 0.05762    | 86.84  |
| molcap                   | homolumo                   | 0.02490    | 88.63  |
|                          | experiment                 | -0.00491   | 90.42  |
|                          | scf                        | 0.06592    | 86.39  |
|                          | exp&scf                    | 0.00613    | 89.52  |
|                          | scf&logp                   | 0.08154    | 85.50  |
|                          | homo&yield&logp&tpsa       | 0.09033    | 84.60  |
| homolumo                 | experiment                 | 0.07617    | 85.50  |
|                          | scf                        | 0.02393    | 88.63  |
|                          | exp&scf                    | 0.06348    | 86.39  |
|                          | scf&logp                   | 0.13379    | 82.36  |
|                          | homo&yield&logp&tpsa       | 0.27539    | 73.86  |
| experiment               | scf                        | -0.01459   | 90.87  |
|                          | exp&scf                    | 0.62891    | 51.03  |
|                          | scf&logp                   | 0.02917    | 88.18  |
|                          | homo&yield&logp&tpsa       | 0.01782    | 89.08  |
| scf                      | exp&scf                    | 0.33984    | 70.28  |
|                          | scf&logp                   | 0.63281    | 50.81  |
|                          | homo&yield&logp&tpsa       | 0.37695    | 68.04  |
| exp&scf                  | scf&logp                   | 0.28906    | 73.41  |
|                          | homo&yield&logp&tpsa       | 0.19629    | 78.78  |
| scf&logp                 | homo&yield&logp&tpsa       | 0.55078    | 56.62  |

-------------------------

## Section 2: Supplementary evidence of agnostic backbone

> Our framework is agnostic to the backbone and the effectiveness of key modules are validated by ablation study under the same backbone setting. Besides, we also supplement the results by changing the backbone into Vicuna 7B. To save the time, we implement the unify SFT on subsets with only 4 tasks. As shown in Table below, the results clearly indicate that the performance advantage is attributable to the larger parameter size of Vicuna.

**Table 3: Comparison results on forward prediction.**
| Model              | Exact | BLEU  | Levenshtein | MACCS | RDK   | MORGAN |
|--------------------|--------|-------|-------------|--------|--------|--------|
| Ours w. Vicuna 7B  | 0.285  | 0.936 | 16.862      | 0.768 | 0.610 | 0.557  |
| Ours w. Llama3 1B  | 0.279  | 0.923 | 17.027      | 0.759 | 0.603 | 0.555  |

**Table 4: Comparison results on LogP prediction.**
| Model              | MAE    |
|--------------------|--------|
| Ours w. Vicuna 7B  | 0.5182 |
| Ours w. Llama3 1B  | 0.6690 |

**Table 5: Comparison results on molecule captioning.**
| Model      | BLEU-2 | BLEU-4 | ROUGE-1 | ROUGE-2 | ROUGE-L | METEOR |
|------------|--------|--------|---------|---------|---------|--------|
| Vicuna 7B  | 0.483  | 0.390  | 0.559   | 0.386   | 0.493   | 0.522  |
| Ours       | 0.455  | 0.361  | 0.549   | 0.381   | 0.487   | 0.503  |

**Table 6: Comparison results on solvent prediction.**
| Model     | Exact  | BLEU   | Levenshtein | MACCS  | RDK    | MORGAN | Validity |
|-----------|--------|--------|-------------|--------|--------|--------|----------|
| Vicuna 7B | 0.2848 | 0.6203 | 4.0710      | 0.4541 | 0.4296 | 0.3924 | 0.999    |
| Ours      | 0.2810 | 0.6020 | 4.2140      | 0.4530 | 0.4250 | 0.3879 | 0.999    |


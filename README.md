# NWIKI and NICE: N-tuple temporal knowledge graph datasets.

<!-- The NWIKI and NICE datasets of the NE-Net model for EMNLP 2024 paper: [Temporal Knowledge Graph Reasoning Based on N-tuple Modeling](https://openreview.net/pdf?id=xQbFsx8usC) -->
NWIKI and NICE are two n-tuple temporal knowledge graph datasets, where each fact contains not only core entities but also auxiliary ones. If you use these datasets, please cite: Hou Z, Jin X, Li Z, et al. "Temporal Knowledge Graph Reasoning Based on N-tuple Modeling" EMNLP 2023. You can find the PDF [here](https://openreview.net/pdf?id=xQbFsx8usC).
## About NWIKI 
NWIKI was constructed as follows:
<!-- [Google](https://www.google.com) -->
- We downloaded the [Wikidata dump](https://archive.org/details/wikibase-wikidatawiki-20171120)  and extracted the facts which contain the timestamp information and involve human entities; 
- To extract n-tuple predicate instances, we selected predicates with more than 3 role types and retained their corresponding predicate instances; 
- We filtered out entities of low frequency, as their behaviors are difficult to learn and predict for most data-driven based methods. 
Correspondingly, facts involving these entities were also filtered out; 
- The instances of the "Position Held" predicate comprise over 50\% of the dataset. 
However, the filtering operation in the previous step could impair connectivity. 
- To maintain a robust connection with other predicates, 
we retained facts that are associated with other predicates and share core entities with the "Position Held" instances; 
- Following [RE-NET](https://arxiv.org/pdf/1904.05530), all facts were split into the training set, the validation set, and the test set by a proportion of 80\%:10\%:10\% according to the time ascending order.


The statistics of NWIKI are displayed as follows, where #Train, #Valid and #Test are the sizes of the training set, the validation set and the test set, respectively.

| Dataset | Binary | N-tuple | Overall | Timestamps | Time Interval |
|:-------:|:------:|:----:|:-------:|:----------:|:-------------:|
| #Train   |  20,686    | 87,711    | 108,397      | 191        | 1 year        |
| #Valid    | 1,847      | 12,523    | 14,370       | 6        | 1 year        |
| #Test    |  2,438     | 13,153 | 15,591    |8        | 1 year         |

## About NICE 
NICE was constructed as follows:
- We collected the raw event records from [ICEWS](https://dataverse.harvard.edu/dataverse/icews) from Jan 1, 2005 to Dec 31, 2014; 
- From these raw event records, we extracted core entities, timestamps, and partial auxiliary information, i.e., the occurrence places. 
- We observed that the predicate names contain additional auxiliary information. 
For example, the predicate names “Cooperate Economically” and “Engage in Judicial Cooperation” contain the specified cooperation aspects of the general predicate “Engaged in Cooperation”, namely “Economic” and “Militarily”, respectively. 
To obtain such auxiliary information, we designed rule templates to extract them from the specified predicate names and merged these specified predicates into the general ones. 
- Considering the absence of role information in the raw event records, we manually assigned role names to each predicate. 
- Similar to NWIKI, NICE was also split into the training set, the validation set, and the test set by a proportion of 80\%:10\%:10\%.


### Dataset Statistics

The statistics of NICE are displayed as follows, where #Train, #Valid and #Test are the sizes of the training set, the validation set and the test set, respectively.

| Dataset | Binary | N-tuple | Overall | Timestamps | Time Interval |
|:-------:|:------:|:----:|:-------:|:----------:|:-------------:|
| #Train   |  46,176    | 322,692    | 368,868      | 3,243        | 24 hours        |
| #Valid    |5,395      | 40,907    | 46,302       | 403        | 24 hours        |
| #Test    |  5,268     | 40,891 | 46,159   |370        | 24 hours         |

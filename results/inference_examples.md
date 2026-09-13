# Post-inference examples — chunking strategies vs routed framework

### SQuAD — post-inference outputs

**Question:** According to Oxfam, the 85 richest people have wealth equal to how many average people?

**Reference answer:** about 3.5 billion people

| Config | Faithfulness | Ans. relevancy | Generated answer |
|---|---|---|---|
| fixed | 1.00 | 0.77 | According to Oxfam, the 85 richest people have wealth equal to that of the bottom 50% of the world's population, or about 3.5 billion people. |
| overlapping | 1.00 | 0.77 | According to Oxfam, the 85 richest people have wealth equal to that of the bottom 50% of the world's population, or about 3.5 billion people. |
| semantic | 1.00 | 0.77 | According to Oxfam, the 85 richest people have wealth equal to that of the bottom 50% of the world's population. |
| **framework (routed)** | 1.00 | 0.77 | According to Oxfam, the 85 richest people have wealth equal to that of the bottom 50% of the world's population, or about 3.5 billion people. |

**Retrieved context (first chunk):**

- *fixed:* to a Los Angeles Times analysis of the report, the wealthiest 1% owns 46% of the world's wealth; the 85 richest people, a small part of the wealthiest 1%, own about 0.7% of the human population's wealth, which is the same as the bottom half...
- *overlapping:* individuals in the world have a combined wealth equal to that of the bottom 50% of the world's population, or about 3.5 billion people. According to a Los Angeles Times analysis of the report, the wealthiest 1% owns 46% of the world's wealt...
- *semantic:* A study by the World Institute for Development Economics Research at United Nations University reports that the richest 1% of adults alone owned 40% of global assets in the year 2000. The three richest people in the world possess more finan...
- *framework:* to a Los Angeles Times analysis of the report, the wealthiest 1% owns 46% of the world's wealth; the 85 richest people, a small part of the wealthiest 1%, own about 0.7% of the human population's wealth, which is the same as the bottom half...

---
### SQuAD — post-inference outputs

**Question:** Besides the walk to the church, what else was left out of the day's celebration?

**Reference answer:** wedding banquet

| Config | Faithfulness | Ans. relevancy | Generated answer |
|---|---|---|---|
| fixed | 0.00 | 0.00 | The context provided does not contain information about a walk to the church or what else was left out of the day's celebration. Therefore, I cannot provide an answer to the questi |
| overlapping | 0.00 | 0.00 | The context provided does not contain information about a "walk to the church" or what else was left out of the day's celebration. Therefore, I cannot provide an answer to the ques |
| semantic | 1.00 | 0.56 | The wedding banquet. |
| **framework (routed)** | 0.00 | 0.00 | The context provided does not contain information about a walk to the church or what else was left out of the day's celebration. Therefore, I cannot provide an answer to the questi |

**Retrieved context (first chunk):**

- *fixed:* Like other historic Christian churches, The United Methodist Church has official liturgies for services of Holy Communion, baptism, weddings, funerals, ordination, anointing of the sick and daily office prayer services. Some clergy offer he...
- *overlapping:* these, there are also special services for holy days such as All Saints Day, Ash Wednesday, Maundy Thursday, Good Friday, and Easter Vigil. These services are contained in The United Methodist Hymnal and The United Methodist Book of Worship...
- *semantic:* The ceremonial walk to the church and the wedding banquet were left out, and were made up two weeks later on 27 June....
- *framework:* Like other historic Christian churches, The United Methodist Church has official liturgies for services of Holy Communion, baptism, weddings, funerals, ordination, anointing of the sick and daily office prayer services. Some clergy offer he...

---
### MMLU — post-inference outputs

**Question:**  In Buddhism, what are ordained women known as?

**Reference answer:** Bhikshunis

| Config | Faithfulness | Ans. relevancy | Generated answer |
|---|---|---|---|
| fixed | 1.00 | 0.86 | Bhikkhunis |
| overlapping | 1.00 | 0.86 | Bhikkhunis |
| semantic | 1.00 | 0.86 | Bhikkhunis |
| **framework (routed)** | 1.00 | 0.86 | Bhikkhunis |

**Retrieved context (first chunk):**

- *fixed:* American woman to be ordained as a Buddhist nun in the Tibetan Buddhist tradition. 1988: Jetsunma Ahkon Lhamo, an American woman formerly called Catharine Burroughs, became the first Western woman to be named a reincarnate lama. 1996: Throu...
- *overlapping:* Khenmo Drolma, an American woman, became the first bhikkhuni (fully ordained Buddhist nun) in the Drikung Kagyu lineage of Buddhism, traveling to Taiwan to be ordained. 2002: A 55-year-old Buddhist nun, Varanggana Vanavichayen, became the f...
- *semantic:* However, this law was revoked some time after Varanggana Vanavichayen became the first female monk to be ordained in Thailand in 2002. 1966: Freda Bedi, a British woman, became the first Western woman to take ordination in Tibetan Buddhism....
- *framework:* However, this law was revoked some time after Varanggana Vanavichayen became the first female monk to be ordained in Thailand in 2002. 1966: Freda Bedi, a British woman, became the first Western woman to take ordination in Tibetan Buddhism....

---
### MMLU — post-inference outputs

**Question:** A chemical agent is found to denature all enzymes in the synaptic cleft. What effect will this agent have on acetylcholine?

**Reference answer:** Acetylcholine will not be degraded in the synaptic cleft.

| Config | Faithfulness | Ans. relevancy | Generated answer |
|---|---|---|---|
| fixed | 0.00 | 0.76 | The agent will prevent acetylcholine from being broken down, leading to an accumulation of acetylcholine in the synaptic cleft. |
| overlapping | 1.00 | 0.78 | The agent will prevent acetylcholine from binding to its receptors, leading to a failure in muscle contraction. |
| semantic | 0.00 | 0.79 | The chemical agent will prevent acetylcholine from being broken down, leading to an accumulation of acetylcholine in the synaptic cleft. |
| **framework (routed)** | 0.00 | 0.79 | The chemical agent will prevent acetylcholine from being broken down, leading to an accumulation of acetylcholine in the synaptic cleft. |

**Retrieved context (first chunk):**

- *fixed:* destroy nicotinic acetylcholine receptors (AChR) at the junction between the nerve and muscle. This prevents nerve impulses from triggering muscle contractions. Most cases are due to immunoglobulin G1 (IgG1) and IgG3 antibodies that attack ...
- *overlapping:* the presence of ubiquitous esterases. It inhibits nicotinic acetycholine and muscarinic acetylcholine receptors and disrupts prolactin and luteinizing hormone levels in the pituitary gland. === Regulation of the pituitary gland === Studies ...
- *semantic:* The effects of neuromodulators are distributed throughout the CPG network. Specially, dopamine was shown to affect cellular and synaptic properties of nearly all components of the crustacean pyloric network. Moreover, dopamine can have oppo...
- *framework:* The effects of neuromodulators are distributed throughout the CPG network. Specially, dopamine was shown to affect cellular and synaptic properties of nearly all components of the crustacean pyloric network. Moreover, dopamine can have oppo...

---

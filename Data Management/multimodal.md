## Multimodal Data Management
| Paper | Conference | Remark |
| :---:| :---:| :---:|
|[Learned Data-aware Image Representations of Line Charts for Similarity Search](https://dl.acm.org/doi/pdf/10.1145/3588942)|sigmod2023|一种从数据相似度和图像相似度两个层面检索line chart的方法。作者研究的是在只提供image而不提供数据的情景下进行相似查询。提出LineNet模型，一个基于vision transformer的三元自编码器，目的是将linechart的chart学习为与其data相关联的一种表征，以至于在每次query时获得表征并在embedding space中进行近邻搜索，精确区分chart背后的data distribution。三个难点：a.设计一个能够同时捕捉chart特点和数据分布进而学习表征的模型；b.没有足够的chart-data对来支撑模型的训练；c.如何得到有代表性的训练样本。为解决b作者自己创建了一个110K的chart-data数据集，并众包了带标签的进行评估。LineNet的训练是有监督的，需要带有相似/不相似标签的charts，也就是训练样本的问题c，作者提出伪标签机制，将chart的data用来做distance计算，并设定阈值，低于便是similar，这样便得到了data aware image similarity。经过伪标签的计算后就得到了三元组：anchor，positive，negative，对应三个自编码器，训练目标是降低正样本与anchor的距离，提升负样本与anchor的距离。部署LineNet时，将查询图片编码再近邻查询就可|
|[DATACOMP:In search of the next generation of multimodal datasets](https://proceedings.neurips.cc/paper_files/paper/2023/file/56332d41d55ad7ad8024aac625881be7-Paper-Datasets_and_Benchmarks.pdf)|nips2023|
|[Provable Dynamic Fusion for Low-Quality Multimodal Data](https://proceedings.mlr.press/v202/zhang23ar/zhang23ar.pdf)|ICML2023|
|[Multimodal Prompting with Missing Modalities for Visual Recognition](https://arxiv.org/pdf/2303.03369.pdf)|CVPR2023|
|[MUST: An Effective and Scalable Framework for Multimodal Search of Target Modality](https://arxiv.org/pdf/2312.06397.pdf)|ICDE2024||
|[Multi-Modal Knowledge Graph Transformer Framework for Multi-Modal Entity Alignment](https://aclanthology.org/2023.findings-emnlp.70.pdf)|EMNLP2023|
|[DEMYSTIFYING CLIP DATA](https://arxiv.org/abs/2309.16671)||The paper aims to reveal CLIP's data curation approach and present a transparent algorithm called MetaCLIP to curate high-quality image-text data from raw web data.Metadata plays a central role in mitigating noise and preserving signal.Balancing the distribution is key to maximizing diversity and task-agnostic properties. Sub-string matching acts as an implicit filter to remove noise without manual rules.Curation algorithm enables easy adaptation to new data sources without external filters. MetaCLIP outperforms CLIP's data, showing the effectiveness of the curation approach.|
|[MixGen: A New Multi-Modal Data Augmentation](https://arxiv.org/pdf/2206.08358.pdf)|WACV2023||
|[Towards Semantic Consistency: Dirichlet Energy Driven Robust Multi-Modal Entity Alignment](https://link.zhihu.com/?target=https%3A//arxiv.org/pdf/2401.17859.pdf)|ICDE2024|
|[Multimodal Graph Learning for Cross-Modal Retrieval](https://epubs.siam.org/doi/pdf/10.1137/1.9781611977653.ch17)|SDM2023|

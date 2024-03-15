# GT-BEHRT

This repository contains an implemention of GT-BEHRT, as described in [``Graph Transformers on EHRs: Better Representation Improves Downstream Performance'' (Poulain et al.)](https://openreview.net/forum?id=pe0Vdv7rsL) published in ICLR 24.



Following the success of transformer-based methods across various machine learning applications, their adoption to healthcare predictive tasks using electronic health records (EHR) has also expanded extensively. Similarly, graph-based methods have been shown to be very effective in capturing inherent graph-type relationships in EHRs, leading to improved downstream performance. Although integrating these two families of approaches seems like a natural next step, in practice, creating such a design is challenging and has not been done. This is partly due to known EHR problems, such as high sparsity, making extracting meaningful temporal representations of medical visits challenging. In this study, we propose GT-BEHRT, a new approach that leverages temporal visit embeddings extracted from a graph transformer and uses a BERT-based model to obtain more robust patient representations, especially on longer EHR sequences. The graph-based approach allows GT-BEHRT to implicitly capture the intrinsic graphical relationships between medical observations, while the BERT model extracts the temporal relationships between visits, loosely mimicking the clinicians' decision-making process. As part of our method, we also present a two-step pre-training strategy for learning better graphical and temporal representations. Our proposed method achieves state-of-the-art performance in a variety of standard medical predictive tasks, demonstrating the versatility of our approach.

##### Citing GT-BEHRT:
GT-BEHRT's original paper is available at [ICLR 24](https://openreview.net/forum?id=pe0Vdv7rsL).
If you find our work useful, please consider the following citation.

```
@inproceedings{
poulain2024graph,
title={Graph Transformers on {EHR}s: Better Representation Improves Downstream Performance},
author={Raphael Poulain and Rahmatollah Beheshti},
booktitle={The Twelfth International Conference on Learning Representations},
year={2024},
url={https://openreview.net/forum?id=pe0Vdv7rsL}
}
```

#### GT-BEHRT's Architecture
<figure>
  <img
  src="https://github.com/healthylaife/GT-BEHRT/blob/main/images/architecture.png"
  alt="GT-BEHRT Architecture.">
  <figcaption>The blue block describes extracting the graph visit embeddings, where C0, C1, ..., C4 represent four exemplar medical codes associated with the visit t of a fictional patient. The medical codes are color-coded to represent different code types (condition, medication, procedure). The graph is based on the medical codes associated to a given visit (visit there). Each visit goes through this process individually before being fed to the Transformer Encoder.
</figcaption>
</figure>

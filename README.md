# ICL consistency data
Repository to provide a URI for the GenBench ICL-consistency task.

You can load the data using 🤗's datasets (click [here](https://huggingface.co/datasets/LucasWeber/icl_consistency_test) to find the dataset on the hub)

#####################################################

# The ICL consistency test

This 🤗 dataset provides data for the [GenBench CBT task 'The ICL consistency test'](https://github.com/GenBench/genbench_cbt/tree/main/src/genbench/tasks/icl_consistency_test).
The ICL consistency test measures the consistency of LLM predictions on the same data points across many different equivalent prompting setups. 
The score in the associated metric (Cohen's kappa) can be understood as a measure of a model's prediction consistency in the face of task-irrelevant information.

For an easy evaluation of any 🤗 models, we refer to the code provided in the GenBench task. For in-depth information on the task, we refer to the associated 
publications ([Weber et al., 2023](https://arxiv.org/abs/2312.04945),[2023](https://aclanthology.org/2023.conll-1.20/)) and the respective GenBench [doc.md](https://github.com/GenBench/genbench_cbt/blob/main/src/genbench/tasks/icl_consistency_test/doc.md).

Evaluation on the relevant metrics can be done via the _example_evaluation.py_ script in the [GenBench repository](https://github.com/GenBench/genbench_cbt/blob/main/src/genbench/tasks/icl_consistency_test/).

### Dataset Description

_Abstract_: The ICL consistency test measures the consistency of LLM predictions on the same data points across many different prompting setups. Different setups are defined by "factors". 
On the one hand, factors can be specific attributes of the used prompt (e.g. the number of examples the model is presented with ["n_shots"] or the type of instructions 
that were used to wrap a specific datapoint ["Instructions"]). On the other hand, the analysis can also be augmented by factors that are related to the way a model is 
evaluated (e.g. whether a model is calibrated) or the type of model that is evaluated (e.g. the number of parameters or instructions tuning). These external factors can 
be added to the analysis by using the task.add_factor() method. The output metric is Cohen's kappa for each factor across all different conditions. A kappa value close to 
1 indicates that the factors do not change the model prediction, while a factor close to 0 strongly changes model predictions. The ICL consistency test has two subtasks, 
one evaluating the ANLI-dataset ([Nie et al., 2019](https://aclanthology.org/N18-1101/)); the other the MNLI-dataset ([Wang et al., 2017](https://aclanthology.org/N18-1101/)).

_Size_: Each subtask contains 57600 when using the full 600 data_IDs. The user can choose to reduce the number of evaluated data_IDs.

## Citation
This dataset was used in the following publications. If you use it, please consider citing the following references:
**BibTeX:**
```
@inproceedings{weber2023mind,
  title={Mind the instructions: a holistic evaluation of consistency and interactions in prompt-based learning},
  author={Weber, Lucas and Bruni, Elia and Hupkes, Dieuwke},
  booktitle={Proceedings of the 27th Conference on Computational Natural Language Learning (CoNLL)},
  pages={294--313},
  year={2023}
}
```
```
@article{weber2023icl,
  title={The ICL Consistency Test},
  author={Weber, Lucas and Bruni, Elia and Hupkes, Dieuwke},
  journal={arXiv preprint arXiv:2312.04945},
  year={2023}
}
```

# Are Experts Needed? On Human Evaluation of Counselling Reflection Generation


## Dataset Introduction

Reflection is a crucial counselling skill where the therapist conveys to the client their interpretation of what the client said. Language models have recently been used to generate reflections automatically, but human evaluation is challenging, particularly due to the cost of hiring experts. Laypeople-based evaluation is less expensive and easier to scale, but its quality is unknown for reflections. Therefore, we explore whether laypeople can be an alternative to experts in evaluating a fundamental quality aspect: coherence and context-consistency. We do so by asking a group of laypeople and a group of experts to annotate both synthetic reflections and human reflections from actual therapists. We find that both laypeople and experts are reliable annotators and that they have moderate-to-strong inter-group correlation, which shows that laypeople can be trusted for such evaluations. We also discover that GPT-3 mostly produces coherent and consistent reflections, and we explore changes in evaluation results when the source of synthetic reflections changes to GPT-3 from the less powerful GPT-2.


## Dataset Format
The dataset is stored in `annotations.csv`, in the same folder as this README. **Each row represents the annotation of a single reflection by a single annotator**.

`annotations.csv` has the following columns:
* `annomi_dialogue_id`: the ID of the AnnoMI dialogue that `dialogue_context` comes from.
* `stage`: in which stage the annotation was done. One of {"GPT-2 stage", "GPT-3 stage"}.
* `dialogue_context`: dialogue context of `reflection`. Use json.loads to read as a dict.
* `reflection_source`: where `reflection` comes from. One of {"BART", "GPT-2", "GPT-3", "Human"}.
* `reflection`: the reflection text.
* `annotator`: anonymised annotator. If the annotator was an expert, this is one of {Expert 1, Expert 2, ..., Expert 9}. If the annotator was a layperson, this is one of {Layperson 1, Layperson 2, ..., Layperson 9}.
* `coherent_and_context_consistent`: whether the reflection is annotated as coherent and context-consistent. One of {"Yes", "No"}.
* `dialogue_contradicting`: whether the reflection is annotated as dialogue-contradicting. N/A if `coherent_and_context_consistent` is "Yes".
* `malformed`: whether the reflection is annotated as malformed. N/A if `coherent_and_context_consistent` is "Yes".
* `off_topic`: whether the reflection is annotated as off-topic. N/A if `coherent_and_context_consistent` is "Yes".
* `on_topic_but_unverifiable`: whether the reflection is annotated as on-topic but unverifiable. N/A if `coherent_and_context_consistent` is "Yes".
* `parroting`: whether the reflection is annotated as parroting. N/A if `coherent_and_context_consistent` is "Yes".


## Dataset License
* This dataset is publicly available under the CC BY-NC license (research purposes only).
* LICENSE file is in the same folder as this README.


## Citation
If you use this dataset in your research, you can cite our paper (link will be available soon) in the format below:
```bash
@inproceedings{are-experts-needed,
    title={Are Experts Needed? On Human Evaluation of Counselling Reflection Generation},
    author = "Wu, Zixiu  and
      Balloccu, Simone  and
      Reiter, Ehud  and
      Helaoui, Rim  and
      Recupero, Diego Reforgiato  and
      Riboni, Daniele",
    booktitle={Proceedings of the 61st Annual Meeting of the Association for Computational Linguistics},
    year={2023}
}
```

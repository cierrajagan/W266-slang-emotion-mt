Does Chinese internet slang cause more emotion loss in Chinese→English machine translation, and does giving the translator slang definitions reduce that loss?

## Repo layout

notebooks/
  01_download_data.ipynb: downloads all datasets and saves tidy copies
data/ : created by the notebook
  raw/: files exactly as downloaded
  processed/ : clean CSV / JSON to be used by later notebooks


## Getting the data

Run notebooks/01_download_data.ipynb top to bottom. It downloads:

| Dataset | What it is | 
|---|---|
| SMP2020-EWECT | ~48k Weibo posts, 6 emotion labels |
| HADQAET | 5,538 Weibo posts + Google MT + human emotion-preservation error annotations |
| CHEER | 1,127 Chinese internet buzzwords with definitions and example posts |

Outputs in data/processed/:

- smp2020_ewect.csv: post_id, subset, split, orig_id, text, label
- hadqaet_annotated.csv: source, MT, emotion_labels, error_types, error_severity, smp_post_id
- hadqaet_keywords.csv, hadqaet_post_edits.csv
- cheer_lexicon.csv: buzzword, definition, description, n_examples, n_chars
- cheer_examples.json: buzzword → list of example posts

The data/ folder is not committed!

## Setup

pip install -r requirements.txt

## References

- Qian et al. (2023). Evaluation of Chinese-English Machine Translation of Emotion-Loaded Microblog Texts. EAMT.
- Huang et al. (2025). Can Large Language Models Understand Internet Buzzwords Through User-Generated Content. ACL.
- SMP2020-EWECT: The Evaluation of Weibo Emotion Classification Technology, SMP 2020 (HIT-SCIR).

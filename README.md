# Voting or Consensus? Decision-Making in Multi-Agent Debate

This repository contains the code, experiments, and data for our paper:

> **Voting or Consensus? Decision-Making in Multi-Agent Debate**  
> *Lars Benedikt Kaesberg, Jonas Becker, Jan Philip Wahle, Terry Ruas, Bela Gipp*

Our work systematically investigates how **multi-agent** Large Language Model (LLM) systems can collaborate on **knowledge** and **reasoning** tasks through debate. We show that:
- **Consensus-based decision protocols** generally outperform others in **knowledge tasks**.
- **Voting-based decision protocols** perform better in **reasoning tasks**.
- **Answer diversity** (achieved through independent drafting and limited communication) substantially boosts performance across the board.

---

## Introduction
While humans have long relied on collaboration to solve complex problems, **decision-making** processes are critical to selecting, refining, and finalizing solutions. We adapt this paradigm to **multi-agent LLM** setups: each agent proposes solutions, debates them, and a **decision protocol** determines the final answer. Our experiments isolate the effect of different decision mechanisms (majority vote, consensus, etc.) on diverse **knowledge** and **reasoning** tasks, highlighting task-specific differences. We also introduce methods to **encourage diversity of thought** among agents, leading to measurable performance gains.

---

## Installation and Basic Setup

1. **Python 3.9+**  
   Ensure you have Python 3.9 or higher installed.

2. **Install MALLM**  
   This project depends on [MALLM](https://pypi.org/project/mallm/). To install:
   ```bash
   pip install mallm
   ```

3. **Prepare Datasets**  
   Place your dataset JSON files in a directory like `data/datasets/`. The exact filenames should match what’s specified in your experiment config files (e.g., `data/datasets/<DATASET NAME>.json`). Instructions on how to get these dataset files can be found on [MALLM](https://pypi.org/project/mallm/).

---

## Running the Experiments

1. **Edit the Batch Config Files**  
   In each JSON configuration (e.g., `experiment1.json`, `experiment2.json`, etc.), update the placeholders such as:
   - `<DATASET NAME>`
   - `<LLM API HOSTNAME>`
   - `<LLM API KEY>`
   - `<MODEL NAME>`
   - `<SAMPLES FOR DATASET>`  

2. **Run a Batch**  
   From your terminal, execute:
   ```bash
   mallm-batch <PATH_TO_BATCH_FILE>
   ```
   The results will be stored in the directory specified by `output_json_file_path` (commonly `./results`).

3. **Evaluation**  
   After collecting results, you can evaluate them with:
   ```bash
   mallm-evaluate --metrics [<METRIC_FOR_DATASET>, ...] ./results
   ```
   Replace `<METRIC_FOR_DATASET>` with the relevant evaluation metric (e.g., `accuracy`, `f1`, etc.).

---

## Citation
If you find this work helpful, please consider citing:

```
@inproceedings{kaesberg-etal-2025-voting,
    title = "Voting or Consensus? Decision-Making in Multi-Agent Debate",
    author = "Kaesberg, Lars Benedikt  and
      Becker, Jonas  and
      Wahle, Jan Philip  and
      Ruas, Terry  and
      Gipp, Bela",
    editor = "Che, Wanxiang  and
      Nabende, Joyce  and
      Shutova, Ekaterina  and
      Pilehvar, Mohammad Taher",
    booktitle = "Findings of the Association for Computational Linguistics: ACL 2025",
    month = jul,
    year = "2025",
    address = "Vienna, Austria",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2025.findings-acl.606/",
    doi = "10.18653/v1/2025.findings-acl.606",
    pages = "11640--11671",
    ISBN = "979-8-89176-256-5"
}
```

---

## License
This project is licensed under [Apache 2.0](LICENSE).

---

*Thank you for your interest in our work! Please reach out with any questions or feedback.*

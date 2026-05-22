# CCLUPE Dataset

**CCLUPE: Credit Context Log Understanding and Prediction Evaluation** is a benchmark for evaluating whether large language models can reason over credit context, structured account fields, and time-series transaction logs for underwriting-style credit analysis.

The released benchmark logs are **fully synthetic**. They are not raw production bank statements and do not contain real customer records, account numbers, or proprietary partner data. The synthetic logs are generated from expert-guided behavioral templates and calibrated to authentic underwriting patterns through statistical screening, schema validation, arithmetic checks, and domain-expert review.

This repository provides the public benchmark data and documentation for CCLUPE. The benchmark covers personal and micro-enterprise clients, with questions designed to test grounded reasoning over transaction-log evidence rather than general financial knowledge alone.

<img width="1124" height="403" alt="CCLUPE overview" src="https://github.com/user-attachments/assets/1dbbe172-2e48-4e92-bbee-17e5d3885982" />

<img width="1202" height="796" alt="CCLUPE dataset taxonomy" src="https://github.com/user-attachments/assets/3854ec36-a7e8-4c06-ac7a-733067268854" />

## Clarifications

- The released transaction logs are synthetic and expert-guided, not authentic customer transaction logs.
- CCLUPE stands for **Credit Context Log Understanding and Prediction Evaluation**.
- Synthetic fidelity is described conservatively: generated logs are calibrated to underwriting-relevant patterns but should not be interpreted as de-identified real statements.
- Quality control uses deterministic answer checks, expert review, and a stratified multi-reviewer validation subset for difficult or underrepresented items.
- The release is intended for benchmark research and model evaluation.

## Dataset Statistics

| Feature | Value |
| :--- | :--- |
| Total Items | 4,062 |
| Client Types | 2: Personal and Micro-enterprise |
| Core Knowledge Domains | 7 |
| Cognitive Levels | 4 |
| Sub-Transaction Types | 16 |
| Question Types | 3: single-choice, multi-choice, calculation |

## Benchmark Structure

CCLUPE evaluates models across four cognitive levels:

- **Memory and Recognition**: identifying explicit transaction patterns.
- **Comprehension and Calculation**: computing financial quantities and interpreting derived indicators.
- **Analysis and Synthesis**: integrating multiple transaction-log signals into a coherent risk profile.
- **Evaluation and Inference**: making higher-order judgments from evidence across the full log.

The benchmark covers credit-log domains such as cash-flow stability, cash-flow behavior, structure and concentration, temporal characteristics, specialized transaction behavior, liquidity pressure, and other underwriting-relevant signals.

## Data Format

The current public file is `final_data.csv`. It contains 4,062 benchmark samples, one CSV row per sample. The file may appear to have many more text lines because each row embeds a full-year transaction log as multi-line text inside one CSV cell.

Main columns:

| Column | Meaning |
| :--- | :--- |
| `序号` | Sample ID |
| `流水信息` | Synthetic client identifier |
| `流水内容` | Full transaction log text |
| `问题种类（消费测试问题）` | Question category |
| `问题种类（分类逻辑大类）` | Core knowledge domain |
| `问题种类（分类逻辑小类）` | Fine-grained sub-domain |
| `问题列表` | Question stem and answer options |
| `问题类别` | Question type |
| `问题难度` | Difficulty level |
| `认知维度` | Cognitive level |
| `answer` | Ground-truth answer |

## Privacy and Use

The public data should be treated as synthetic benchmark data. It is designed to preserve transaction-log reasoning structure while avoiding release of real customer records. Any real-looking counterparty, merchant, or institution names in the logs are part of synthetic examples and should not be interpreted as real customer data.

Please use CCLUPE for research on model evaluation, credit-log reasoning, benchmark analysis, and reproducibility studies. The benchmark is not a credit scoring system and should not be used to make real lending decisions.

## Transaction Log Example

| Transaction Date | Counterparty | Amount | Balance | Status/Notes |
| :--- | :--- | :---: | :---: | :--- |
| 2023/03/15 09:30 | Mortgage Repayment Channel | -3,200 | 6,800 | Regular repayment |
| 2023/04/15 09:30 | Mortgage Repayment Channel | 0 | 2,100 | Insufficient funds pattern |
| 2023/06/10 10:20 | Produce Supplier | -5,000 | 12,000 | Procurement expenditure |
| 2023/07/25 16:20 | Business Owner Transfer | -1,200 | 300 | Abnormal liquidity pressure |

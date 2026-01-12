CCLUPE is a benchmark grounded in authentic consumer credit transaction logs, covering both personal and micro-enterprise (SME) clients. Unlike benchmarks limited to general financial knowledge or synthetic data, CCLUPE employs a hierarchical framework with 7 knowledge domains, 16 sub-domains, and 4 cognitive levels. To ensure practical relevance, the dataset and questioning logic were developed in consultation with professional credit underwriters. Their expertise ensures that each evaluation task mirrors the specific spend patterns, risk signals, and decision-making logic critical to real-world loan approvals. This expert-validated structure enables a systematic evaluation of LLMs' credit underwriting and reasoning capabilities in high-stakes financial scenarios.
<img width="1124" height="403" alt="image" src="https://github.com/user-attachments/assets/1dbbe172-2e48-4e92-bbee-17e5d3885982" />
Here we provided showcases CCLUPE, a specialized dataset designed for evaluating the capabilities of Large Language Models (LLMs) in the domain of Credit Card Log Understanding and Personal/Enterprise analysis.

# CCLUPE Dataset

> **Credit Card Log Understanding and Personal/Enterprise analysis**

![CCLUPE Overview](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/0b106263541b446797743d26279f6580~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=2692&h=906&s=1200373&e=png&b=fdfdfd)

## 📊 Dataset Statistics

| Feature | Value |
| :--- | :--- |
| **Total Items** | 4,062 |
| **Client Types** | 2 (Personal & Micro-enterprise) |
| **Core Knowledge Domains** | 7 |
| **Cognitive Levels** | 4 |
| **Sub-Transaction Types** | 16 |
| **Question Types** | 3 |

---

## 🧠 Framework Details

<details>
<summary><b>1. Cognitive Levels</b> (Click to expand)</summary>

*   **Comprehension & Calculation**: Processing basic financial math.
*   **Memory & Recognition**: Recalling specific transaction patterns.
*   **Evaluation & Inference**: Predicting credit risk and fund flow logic.
*   **Analysis & Synthesis**: Aggregating multi-domain financial behaviors.
</details>

<details>
<summary><b>2. Domain Taxonomy</b> (Click to expand)</summary>

The dataset evaluates models across the following dimensions:
*   **Risk Factors**: Penalties, Risky spending, Non-essential expenditures.
*   **Flow Patterns**: Spikes, Seasonality, Liquidity, Refunds.
*   **Operational Context**: Microloans, Overseas, Nighttime transactions.
</details>

---

## 📝 Transaction Log Examples

| Transaction Date | Account Holder | Amount ($) | Balance ($) | Status/Notes |
| :--- | :--- | :---: | :---: | :--- |
| 2023/3/15 9:30 | Mortgage Dept | $-3,200$ | $6,800$ | ✅ Regular Repayment |
| 2023/4/15 9:30 | Mortgage Dept | $0$ | $2,100$ | ❌ **Insufficient Funds** |
| 2023/6/10 10:20 | Chengdong Produce | $-5,000$ | $12,000$ | ✅ Procurement expenditure |
| 2023/7/25 16:20 | Li XX (Legal Person) | $-1,200$ | $300$ | ❌ Abnormal fund withdrawal |

---

## 🔢 Calculation Logic

The dataset challenges LLMs to maintain accurate ledger states using the following balance formula:

$$B_{n} = B_{n-1} + T_{n}$$

Where:
*   $B_{n}$ is the current balance.
*   $T_{n}$ is the transaction amount (negative for spending).

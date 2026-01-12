CCLUPE is a benchmark grounded in authentic consumer credit transaction logs, covering both personal and micro-enterprise (SME) clients. Unlike benchmarks limited to general financial knowledge or synthetic data, CCLUPE employs a hierarchical framework with 7 knowledge domains, 16 sub-domains, and 4 cognitive levels. To ensure practical relevance, the dataset and questioning logic were developed in consultation with professional credit underwriters. Their expertise ensures that each evaluation task mirrors the specific spend patterns, risk signals, and decision-making logic critical to real-world loan approvals. This expert-validated structure enables a systematic evaluation of LLMs' credit underwriting and reasoning capabilities in high-stakes financial scenarios.
<img width="1124" height="403" alt="image" src="https://github.com/user-attachments/assets/1dbbe172-2e48-4e92-bbee-17e5d3885982" />
Here we provided showcases CCLUPE, a specialized dataset designed for evaluating the capabilities of Large Language Models (LLMs) in the domain of Credit Card Log Understanding and Personal/Enterprise analysis.
Category & Details
Data Scale: Contains 4,062 items with diverse transaction logs.
Client Types: Covers Personal Clients (daily spending/repayments) and Micro-enterprise Clients (operational cash flow).
Cognitive Levels: Evaluates 4 levels: Memory & Recognition, Evaluation & Inference, Analysis & Synthesis, and Comprehension & Calculation.
Dimensions: Spans 7 Core Knowledge Domains and 16 Sub-transaction types (e.g., liquidity, essential/non-essential spending, spikes, and seasonality).
Logical Inference: Distinguishing between "Healthy Cash Flow" (left green checks) and "Abnormal/Failed Fund Flow" (right orange crosses) based on transaction notes.
Structured Data Extraction: Converting raw transaction logs into financial insights.
Mathematical Calculation: Using mathematical expressions to compute balances, liquidity ratios, and spending patterns. For instance, calculating a new balance from a previous balance and transaction amount
Taxonomy of Risk: Classifying transactions into categories like "Risky," "Penalties," and "Subscription" to assess creditworthiness.

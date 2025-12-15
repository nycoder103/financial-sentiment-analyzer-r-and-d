Financial Sentiment Analyzer [R&D Sandbox]

"Can we trust a single AI model to understand both a Bloomberg terminal and a Reddit thread?"

This repository serves as my personal Research & Development (R&D) Sandbox for testing advanced NLP architectures. The prototypes and benchmarks developed here act as the foundational research for a larger production system I am currently building with my AI engineering Meetup group.

The goal of this R&D lab is to move beyond "happy path" tutorials and empirically validate how different Transformer models handle the chaotic reality of financial data.

🔬 The Engineering Challenge

In the initial phase of our group project, we hypothesized that industry-standard models like FinBERT would handle all financial sentiment tasks. I built this sandbox to stress-test that assumption before we committed to a production architecture.

The Experiments:

🧪 Experiment 1: The "Reality Check" Benchmark

Hypothesis: A model pre-trained on financial news will perform equally well on social media financial discourse.
Method: I built a custom benchmarking framework (notebooks/Benchmarking_Framework.ipynb) to test models against Financial Phrasebank (News) and Twitter Financial News (Social).
Result: Hypothesis Failed.

News Accuracy: ~97% (FinBERT excels here).

Social Accuracy: ~30% (FinBERT fails to detect sarcasm/slang).

🧪 Experiment 2: The Agentic Quorum

Hypothesis: A multi-agent system combining specialized models can resolve conflicts and improve overall reliability.
Method: I designed an Agentic Quorum architecture (notebooks/Agentic_Quorum.ipynb) where three distinct agents analyze the same input and vote:

The Banker: (FinBERT) - Weighted for formal language.

The Socialite: (Roberta) - Weighted for informal nuance.

The Generalist: (DistilBERT) - Tie-breaker and context provider.
Result: The Quorum successfully filtered out "false negatives" from social data while maintaining high precision on formal news.

🛠️ Technical Implementation

This repository demonstrates my work in the following AI Engineering domains:

Data Pipeline Architecture: Solving the "Time Alignment" problem by synchronizing unaligned sentiment data with Supabase historical market data.

Model Evaluation: Writing custom evaluation loops in PyTorch/Hugging Face to normalize outputs from different model architectures (e.g., mapping [0,1,2] labels to [Negative, Neutral, Positive]).

Visualization: Using Plotly to render dynamic, interactive comparisons of model performance to drive data-driven architectural decisions.

Core Stack

* Language: Python 3.10+

* NLP: Hugging Face transformers, datasets

* Data: Pandas, NumPy, Supabase (PostgreSQL)

* Vis: Plotly Graph Objects

📂 Research Notebooks


* 01_Benchmark_Framework.ipynb

The "Reality Check." Loads 7+ models and benchmarks them against formal vs. informal datasets.

** torch, transformers

* 02_Agent_Quorum_POC.ipynb

The Solution. Implements the voting logic and conflict resolution between multiple agents.

Multi-Agent Design


🚀 Usage & Reproduction

This code is designed to run in Google Colab for GPU acceleration.

Clone the Lab:

git clone [https://github.com/your-username/financial-sentiment-analyzer-r-and-d.git](https://github.com/your-username/financial-sentiment-analyzer-r-and-d.git)


Install Dependencies:

pip install -r requirements.txt


Run the Research:
Open notebooks/01_Benchmark_Framework.ipynb to reproduce the accuracy gap findings.

ℹ️ Authorship & Context

Role: Lead AI Engineer (R&D Phase)
Purpose: This repository contains my personal contributions to the project's research phase. The final production-grade system is being developed in a separate private repository with my team.

My specific contributions shown here:

* Conception and coding of the Benchmarking Framework.

* Design of the Multi-Agent Quorum logic.

"In AI Engineering, the model is just a component. The System is the product."

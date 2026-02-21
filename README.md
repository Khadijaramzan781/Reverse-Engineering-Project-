 AI-Driven Vulnerability Detection & Reverse Engineering

This project explores the capabilities of Large Language Models (LLMs) in identifying security vulnerabilities within **C source code** and **compiled binaries**. By bridging the gap between static analysis and reverse engineering, we achieve high-precision threat detection.

 🌟 Project Overview
Detecting vulnerabilities at the binary level is a challenge due to the loss of semantics during compilation. This project uses state-of-the-art LLMs and **Ensemble Learning** to detect critical flaws (CWEs) in both raw source code and disassembled object files.

 🛠️ Key Features
- **Dual-Level Analysis:** Benchmarked on **Juliet (Source Code)** and **ROMEO (Binaries)** datasets.
- **Ensemble Model:** Combined **CodeBERTa**, **DistilRoBERTa**, and **GraphCodeBERT** using Soft Voting for robust decision-making.
- **Reverse Engineering:** Automated risk scoring of `.o` files using `objdump` disassembly.
- **Advanced Prompting:** Evaluation of Zero-shot, Few-shot, Role-based, and Hybrid prompting strategies.

 📊 Vulnerability Scope (CWEs)
The system is trained to detect the following critical weaknesses:
- **CWE-121:** Stack-based Buffer Overflow
- **CWE-190:** Integer Overflow
- **CWE-416:** Use-After-Free
- **CWE-476:** Null Pointer Dereference
- **CWE-134:** Uncontrolled Format String

 📈 Performance Results
Our Ensemble approach and Hybrid prompting achieved exceptional results:
- **Accuracy:** 99% (Ensemble)
- **Recall:** 1.00 (Zero False Negatives in Hybrid/Ensemble modes)
- **Precision:** 0.98

 📁 Repository Structure
- `Notebooks/`: Jupyter notebooks for Ensemble training and Binary analysis.
- `Documentation/' : Full SSDD Project Report and Paper Analysis.
- `Results/`: Confusion matrices and performance visualizations.

 🚀 How to Use
1. Clone the repository.
2. Install dependencies: `pip install transformers torch`.
3. Run `Reverse_Engineering.ipynb` to analyze ROMEO dataset object files.
4. Run `Ensemble_Model.ipynb` to see the voting mechanism in action.

 📊 Datasets Used

This project utilizes two primary datasets for benchmarking and training:

1. **Juliet Dataset (Source Code):** - A comprehensive suite of C/C++ programs maintained by NIST, containing thousands of labeled examples of various vulnerabilities.
   - **Link:** [NIST Juliet Dataset(https://huggingface.co/datasets/LorenzH/juliet_test_suite_c_1_3)

Models & Methodology
Ensemble Learning: Combined CodeBERTa, DistilRoBERTa, and GraphCodeBERT using Soft Voting to improve detection accuracy and reliability.
Reverse Engineering: Utilized TinyLlama-1.1B alongside the objdump utility to perform static analysis on disassembled binary object files (.o).
Prompt Engineering: Evaluated the performance of Zero-shot, Role-based, and Hybrid prompting strategies.

 🤝 Conclusion
This project demonstrates that AI can significantly enhance the workflow of security auditors by providing a 100% recall rate in identifying critical memory-related vulnerabilities.

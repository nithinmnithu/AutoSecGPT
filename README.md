# AutoSecGPT: AI-Powered Threat Analysis in Automotive Cybersecurity

AutoSecGPT is an AI-powered platform that automates threat modeling and risk assessment for modern connected and autonomous vehicles. It analyzes vehicle architecture (ECUs, communication protocols, external interfaces) using AI reasoning aligned with **STRIDE** and **ISO/SAE 21434** cybersecurity standards, then generates interactive attack graph visualizations and professional risk reports.

Built as a Major Project (22ISP65) at **Nagarjuna College of Engineering and Technology (NCET)**, an Autonomous College under VTU, Belagavi.

---

## 🚗 Overview

Modern vehicles are increasingly connected — CAN bus, V2X communication, over-the-air (OTA) updates, and mobile apps all widen the attack surface for cyber threats such as remote ECU compromise, unauthorized data access, and interference with safety-critical systems.

Traditional signature-based and manual threat modeling methods are too slow to keep up. AutoSecGPT addresses this by using AI (via the OpenAI API) to automate identification of vulnerabilities, calculate risk scores, visualize attack paths, and generate clear, structured security reports — reducing analysis time and improving consistency for automotive cybersecurity engineers.

---

## ✨ Key Features

- **AI-Powered Threat Modeling** — Uses the OpenAI API to analyze vehicle architecture against STRIDE and ISO/SAE 21434 frameworks.
- **Interactive Attack Graph Visualization** — Built with PyVis / vis-network.js, showing how a vulnerability in one ECU can escalate into a system-wide compromise.
- **Automated Risk Assessment** — Computes likelihood, impact, and exploitability to classify each threat as Low, Medium, High, or Critical.
- **CAPEC Analysis** — Cross-references threats against the Common Attack Pattern Enumeration and Classification database for standardized attack patterns.
- **Automated Report Generation** — Exports professional PDF (via PDFKit), JSON, and Markdown reports summarizing vulnerabilities, attack flows, and mitigation strategies.
- **Modular Streamlit Interface** — Dedicated tabs for Threat Model, Attack Model, Security Controls, Attack Graph, Risk Assessment, CAPEC Analysis, and Report generation.

---

## 🏗️ System Architecture

The system follows a 4-stage pipeline:

1. **Input Block** — Collects vehicle architecture details (ECUs, protocols, interfaces) via the Streamlit frontend.
2. **AI Analysis Block** — The OpenAI API analyzes inputs against STRIDE and ISO/SAE 21434 to identify threats and vulnerabilities.
3. **Visualization Block** — PyVis generates interactive attack graphs showing how attacks propagate through vehicle components.
4. **Reporting Block** — Compiles findings into PDF, JSON, and Markdown reports via PDFKit.

<p align="center">
  <img src="docs/architecture_diagram.png" alt="System Architecture" width="700"/>
</p>

<p align="center">
  <img src="docs/block_diagram.png" alt="Block Diagram" width="700"/>
</p>

### Workflow

<p align="center">
  <img src="docs/flowchart.png" alt="Workflow Flowchart" width="500"/>
</p>

---

## 🖥️ Screenshots

| Threat Modeling Interface | Streamlit Application |
|---|---|
| ![Impact Assessment](docs/ui_impact_assessment.jpeg) | ![Streamlit App](docs/ui_streamlit_app.jpeg) |

| Sample Output | Model Accuracy |
|---|---|
| ![Output](docs/output_screenshot.jpeg) | ![Accuracy Plot](docs/accuracy_plot.jpeg) |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | [Streamlit](https://streamlit.io/) |
| Backend | Python 3.x |
| AI Reasoning | OpenAI API |
| Attack Graph Visualization | [PyVis](https://pyvis.readthedocs.io/) / vis-network.js |
| Report Generation | [PDFKit](https://pdfkit.org/) |
| Data Storage | Structured JSON files |
| Standards Followed | ISO/SAE 21434, STRIDE, CAPEC |

---

## 📁 Project Structure

Based on the project's documented file structure:

```
AutoSecGPT/
├── main.py                      # Entry point — run with `streamlit run main.py`
├── requirements.txt              # Python dependencies
├── .streamlit/
│   └── config.toml               # Streamlit theme & layout config
├── tabs/                          # Each file = one functional page in the app
│   ├── threat_model.py            # AI-based threat modeling
│   ├── attack_model.py            # Attack chain generation
│   ├── likelihood_assessment_full.py   # Threat likelihood scoring
│   ├── impact_assessment.py       # Impact severity scoring
│   ├── risk_computation.py        # Final risk score calculation
│   ├── attack_graph.py            # Interactive attack graph generation
│   ├── report.py                  # Report export (PDF/JSON/Markdown)
│   ├── controls.py                # Security controls mapping
│   └── weakness.py                # System weakness identification
├── util/
│   ├── util.py                    # Helper functions
│   ├── sidebar.py                 # Sidebar navigation
│   ├── capec.json                 # CAPEC attack pattern database
│   └── logo.png
├── lib/
│   └── vis-9.1.2/                 # vis-network.js visualization library
├── .files/                        # Auto-generated JSON data (attack models, risk results)
├── docs/                          # Diagrams & screenshots (this repo)
└── README.md
```

> **Note:** This repository currently includes the documented project structure and one recovered source file (`tabs/likelihood_assessment_full.py`) reconstructed from the project report. Add the remaining `.py` files, the `lib/` and `util/` folders, and `.streamlit/config.toml` from your original project folder to complete the codebase.

---

## ⚙️ Getting Started

```bash
# 1. Clone the repository
git clone https://github.com/nithinmnithu/AutoSecGPT.git
cd AutoSecGPT

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the application
streamlit run main.py
```

You'll need an **OpenAI API key** — the app prompts for it in the sidebar ("Model Provider Selection" → "API Key Input") to power the AI-based threat reasoning.

---

## 📊 Results

- **Training Accuracy:** ~97–98% — the model effectively learned patterns from historical automotive cybersecurity data.
- **Validation Accuracy:** ~94–95% — indicating strong generalization to previously unseen threats without overfitting.

---

## 🔮 Future Enhancements

- **Real-Time Data Integration** — Connect to live/simulated CAN bus data streams for dynamic, operational threat monitoring.
- **Expanded Protocol Support** — Extend beyond in-vehicle networks to Ethernet, V2X, and remote telematics APIs.
- **Automatic Mitigation Suggestions** — AI-ranked, specific mitigation strategies (e.g., firewall rules, cryptographic solutions).
- **Interactive 3D Visualization** — Upgrade attack graphs from PyVis to a 3D visualization (e.g., Three.js).
- **Benchmarking & Validation Module** — Benchmark against known threat datasets to measure accuracy vs. traditional manual threat modeling.

---

## 👥 Team

Developed as a Major Project (22ISP65), Department of Information Science and Engineering, NCET:

- Keerthana S — 1NC22IS025
- Saurav Raj — 1NC22IS049
- Shashidhar — 1NC22IS053
- **Nithin M** — 1NC23IS400

**Guide:** Dr. Sanjeevakumar M Hatture, Professor and HOD, Department of ISE, NCET

---

## 📚 References

This project builds on established automotive cybersecurity standards and research, including ISO/SAE 21434, the STRIDE threat modeling framework, and peer-reviewed IEEE/SAE literature on connected and autonomous vehicle security. See the full project report for the complete reference list.

---

## 📄 License

Add your chosen license here (e.g., MIT, Apache 2.0) — not specified in the source project documentation.

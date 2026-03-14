# 🧬 NCBI Gene-Protein Research Agent

<div align="center">

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![AI](https://img.shields.io/badge/AI-Agent-orange.svg)
![NCBI](https://img.shields.io/badge/NCBI-API-lightblue.svg)

**An autonomous system for comprehensive gene/protein analysis with intelligent PubMed integration.**

*Advanced AI Agent for bioinformatics research and molecular data synthesis.*

</div>

## 🎯 Project Overview

This is a high-performance system designed for automated data retrieval and analysis of genes and proteins from NCBI, featuring intelligent, agentic search capabilities within PubMed. Built for researchers who require rapid, structured insights into molecular targets.

### ✨ Key Advantages

- 🧠 **Agentic Reasoning** — Orchestrates LLMs to analyze and summarize multi-modal biological data.
- 🔍 **Deep Parsing** — Comprehensive extraction of 100+ XML fields from NCBI databases.
- 📚 **Intelligent PubMed Retrieval** — Adaptive search strategies with strict anti-hallucination protocols.
- 🛡️ **Error-Resilient Architecture** — Built-in handling for API rate limits and data inconsistencies.
- 🎯 **Domain-Specific Analysis** — Specialized focus on post-translational modifications (PTMs) and aging biology.

## 🚀 Quick Start

### Prerequisites

```bash
Python 3.8+
NCBI API Key
Nebius AI API Key (or other compatible LLM provider)
```

### Installation

1. **Clone the repository:**
```bash
git clone [https://github.com/your-username/ncbi-research-agent.git](https://github.com/your-username/ncbi-research-agent.git)
cd ncbi-research-agent
```

2. **Install dependencies:**
```bash
pip install smolagents requests xmltodict
```

3. **Configure API Keys:**
```bash
# Create key files
echo "your_nebius_api_key" > secret.txt
echo "your_ncbi_api_key" > NCBI_API_KEY.txt
```

4. **Run Analysis:**
```python
from ncbi_agent import final_process

# Execute full pipeline for NRF2
final_process("NRF2")
```

## 🛠️ System Architecture

### Core Modules

#### 🧬 Gene Parser (`extract_ALL_fields_gene`)
- **Full XML Parsing:** Handles 100+ fields from NCBI Gene.
- **Comment Extraction:** Captures pathways, phenotypes, and functional annotations.
- **Genomic Coordinates:** Precise localization of gene loci.
- **Cross-Database Integration:** Linkage to external bio-resources.

#### 🧫 Protein Analyzer (`parse_protein_all_fields`)
- **Feature Analysis:** Domains, sites, and structural motifs.
- **PTM Detection:** Specialized parsing for phosphorylation, methylation, and more.
- **Sequence Extraction:** Retrieval of protein primary structures.
- **Reference Parsing:** Automated extraction of cited publications.

#### 🔍 PubMed Intelligence (`run_super_agent`)
- **Adaptive Querying:** Generates smart queries based on structural data insights.
- **Anti-Hallucination Policy:** Strict grounding rules to prevent model fabrications.
- **Iterative Refinement:** Multiple search cycles for maximum coverage.
- **Aggressive Discovery Mode:** Creative strategies for low-yield search targets.

#### 🧠 AI Summarization (`summarize_ALL_fields_*`)
- **Structured Synthesis:** Organized sections with clear hierarchies.
- **Fact-Only Policy:** Exclusively data-driven insights.
- **Context Optimization:** Efficient token management for long-context windows.

## 📊 Usage Example

```python
# Full analysis pipeline
result = final_process("SOX2")

# Component-level execution:
gene_data = process_gene("6657")      # SOX2 gene ID
protein_data = process_protein("NP_003097.1") # SOX2 protein accession
```

**Output Artifacts:**
- 📄 `gene_protein_report.txt` — Structured analytical report.
- 📚 `pubmed_raw_data.txt` — Raw PubMed metadata.
- 🎯 Statistics on retrieved publications and identified features.

## 🔧 Technology Stack

```text
Core AI:
├── smolagents — Tool-calling agentic framework
├── requests — NCBI API communication layer
├── xml.etree — Data structure parsing
├── OpenAIServerModel — LLM integration (Nebius)
└── MCP Protocol — Tool integration layer

Bio-Integration:
├── E-utils API — Primary data access point
├── Gene DB — Genomic information
├── Protein DB — Proteomic data
├── PubMed — Literature mining
└── Nucleotide — Sequence retrieval
```

## 📁 Project Structure

```text
ncbi-research-agent/
├── ncbi_agent.py              # Core Agent Logic
├── secret.txt                 # LLM API Key
├── NCBI_API_KEY.txt           # NCBI Access Credentials
├── gene_protein_report.txt    # Sample Analysis Output
├── pubmed_raw_data.txt        # Raw Literature Data
└── README.md                  # Documentation
```

## 🧪 Hackathon & Scientific Features

### 🚀 High-Throughput NCBI Protocol
- **Maximum Data Extraction:** Grabs every available feature and annotation.
- **Resilience:** Built to survive API timeouts and malformed responses.
- **Token Conservation:** Optimized prompt engineering for large-scale data.

### 🔬 Protein Engineering Focus
- **Sequence Modifications:** Analysis of mutations, substitutions, and deletions.
- **Functional Impact:** Insights into how changes affect protein function.
- **Longevity Research:** Specialized filtering for aging-associated biomarkers.
- **Engineering Insights:** Suggests potential directions for protein modification.

### 🛡️ Scientific Rigor
- **Verification:** Only facts extracted from abstracts; PMID citations included for every claim.
- **Experimental Priority:** Weights results based on experimental evidence vs. computational predictions.
- **Precision Focus:** Highlights specific amino acid positions and molecular changes.

## 🙏 Acknowledgements

- MCP server components modified from [hamzameer/ncbi-mcp-server](https://github.com/hamzameer/ncbi-mcp-server).
- Powered by the [Model Context Protocol (MCP)](https://github.com/modelcontextprotocol) for tool orchestration.

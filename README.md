# Web-Graph-Analyser

A hyperlink-based network analysis project built using Screaming Frog SEO and Gephi, focused on crawling, cleaning, and visualizing the IIT Kanpur web graph. This repository contains all datasets, scripts, and visualizations used for modularity clustering, PageRank computation, and centrality analysis.

##  Project Overview

This project was developed as part of the **MBA749M - Social Media Analytics** course at IIT Kanpur under the guidance of **Prof. Shankar Prawesh**. The objective was to construct and analyze a large-scale web graph starting from the IIT Kanpur Wikipedia page.

##  Contributors

- **Amipriya Anand (220122)** – Data collection, preprocessing, documentation
- **Harsh Nirmal (220431)** – Graph import, visualization, analysis

##  Methodology

### 1. Data Collection
- Seed URL: `https://en.wikipedia.org/wiki/IIT_Kanpur`
- Tool: **Screaming Frog SEO Spider**
- Iterative crawling and seed expansion using exported `.xlsx` and `.csv` files

### 2. Data Cleaning
- Retained only `From` and `To` columns
- Removed:
  - Duplicate links
  - Protocols (`http://`, `https://`, `www.`)
  - URLs longer than 100 characters
- Final cleaned dataset saved as `cleaned_links1.csv`
- checkout the jupyter notebook `smm.ipynb` for the complete data cleaning and downloading

### 3. Graph Construction
- Imported into **Gephi**
- Applied **Yifan Hu layout** for spatial visualization
- Directed graph with:
  - **Nodes**: 154,381
  - **Edges**: 302,964

##  Analysis Performed

### 🔹 Degree Centrality
- Top-10 nodes ranked by **In-Degree** and **Out-Degree**
- See: `indegree_top 10.csv`

### 🔹 PageRank
- Computed using Gephi’s PageRank algorithm (damping factor = 0.85)
- Node sizes and colors scaled by PageRank
- See: `PageRank` visualization in report

### 🔹 Modularity Clustering
- Detected **41 communities** using Gephi’s modularity algorithm
- Nodes colored by modularity class
- Largest cluster: **Modularity Class 31**
  - **Nodes**: 14,626
  - **Edges**: 53,356
  - Exported as: `mod_class_31.csv`, `final_mod_class_31_links.csv`

##  Repository Structure

| File | Description |
|------|-------------|
| `SMA_project_220122_220431.pdf` | Final project report |
| `Gephi-Project.gephi` | Gephi workspace file |
| `indegree_top 10.csv` | Top-10 nodes by in-degree |
| `highest_modularity_cluster.csv` | Filtered largest cluster |
| `mod_class_31.csv` | Node list for modularity class 31 |
| `final_mod_class_31_links.csv` | Edge list for modularity class 31 |
| `smm.ipynb` | Jupyter notebook for preprocessing |
| `wiki_iitk_step1.xlsx` | Initial crawl output |
| `outlinks_seed_part1.xlsx`, `outlinks_seed_part2.xlsx` | Screaming Frog exports |
| `seeds_step2_part1.csv`, `seeds_step2_part2.csv` | Expanded seed lists |

##  Key Insights

- **High-authority nodes** (e.g., `developer.wikimedia.org`, `mediawiki.org`) dominate in-degree rankings.
- **Wikipedia pages** on global topics (e.g., `New York City`, `India`) show high out-degree due to extensive linking.
- **Modularity clustering** reveals tightly-knit communities, especially among IIT Kanpur-related pages.
- **PageRank** highlights central hubs in the network, useful for understanding influence and visibility.

##  Citation

If you use this repository or its methods, please cite the original project report:


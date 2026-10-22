# Devon Farber | Python Analytics Portfolio

Selected academic projects from Boston University MET CS688, covering data collection, natural language processing, unsupervised learning, and network analysis.

My background spans medicine, business, public health, and graduate study in applied data analytics. These projects demonstrate Python workflows relevant to research and analytics, including healthcare news collection and analysis.

## Project guide

Start with the healthcare news and sentiment notebooks for healthcare-focused examples, then review text clustering and graph analytics for broader analytical methods.

### [Healthcare News Scraping](01_healthcare_news_scraping.ipynb)

Collects healthcare news with Requests and Beautiful Soup, removes duplicate titles, checks missing fields, exports CSV, and plots keyword frequencies.

Recorded output: 50 unique articles. Live search results and page selectors may change.

### [Healthcare Headline Sentiment Analysis](02_healthcare_sentiment_analysis.ipynb)

Compares AFINN lexicon scores with DistilBERT sentiment classifications for healthcare AI headlines and exports an Excel comparison.

Recorded output: 20 headlines, with 5 exact label agreements and 15 disagreements. AFINN includes neutral while this DistilBERT model is binary, so disagreement is not an accuracy measure. Manual themes are tied to the original headline order and must be reassigned after fetching new headlines.

### [Text Clustering and Topic Modeling](03_text_clustering_topic_modeling.ipynb)

Cleans Indiegogo campaign titles, compares bag-of-words preprocessing, applies TF-IDF, LSA, K-means, and LDA, and visualizes topic probabilities.

Recorded output: vocabulary reduced from 20,750 to 4,880 terms (76.48%); LSA plus K-means silhouette score 0.659. This internal clustering score is not predictive accuracy or proof of topic quality. Requires the five original indiegogo_2025_06.csv through indiegogo_2025_10.csv files, which are not included.

### [Graph Analytics](04_graph_analytics.ipynb)

Builds an undirected social network, selects a reproducible connected subgraph, compares Dijkstra and A*, compares Prim and Kruskal minimum spanning trees, and visualizes PageRank and HITS.

Recorded output: a connected 100-node subgraph with 558 edges, drawn from an input table of 29,790 rows. Requires person_knows_person.csv with pipe-separated source and target columns, which is not included. Unit edge weights limit shortest-path and spanning-tree comparisons; mutual edges also limit distinct hub/authority interpretation.

## Running the notebooks

The notebooks were written for Google Colab. Upload a notebook to Colab, supply any required CSV inputs using its upload cell, and run cells from top to bottom. Use a separate runtime or working directory for each project. The clustering notebook reads every CSV in its working directory.

For a local Jupyter environment:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

Replace `google.colab.files` upload/download calls with local file placement or saving when running outside Colab. Notebook shell installation commands are intended for an IPython environment. The graph notebook does not install its dependencies itself; use the requirements file or install pandas, NetworkX, SciPy, and Matplotlib in its runtime.

Internet access is needed for news retrieval, the pretrained sentiment model, and NLTK WordNet resources. Dependencies below are unpinned starting requirements, not a recovered or tested historical environment.

## Data and interpretation

The original CSV inputs and generated spreadsheet/CSV exports were not provided with these notebooks. Saved tables and charts remain available inside the notebooks for review. No substitute datasets have been invented. Source webpages, headlines, and external datasets remain subject to their owners' terms.

These are academic demonstrations, not validated clinical tools. Sentiment confidence scores are model outputs, not clinical evidence. The scraper matches separate title and snippet lists by position, so changes in page structure can cause missing or mismatched records; inspect retrieved records before reuse. The sentiment notebook assigns 20 manual themes by row order, which must be reviewed for any new retrieval.

## Validation of this package

Notebook JSON and Python cell syntax were checked during packaging, allowing for notebook installation commands. Existing recorded outputs were reviewed for the summary above. Analyses were not rerun; live network calls, model downloads, and missing CSV inputs prevent claiming full reproducibility from this package alone.

## Academic provenance

Prepared from Devon Farber's supplied CS688 homework notebooks. Descriptive filenames and introductory markdown were added; analytical code and recorded outputs were retained. Coursework provenance is preserved for transparent review.

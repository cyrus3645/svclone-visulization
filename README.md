# svclone-visulization
svclone-visulization
SVclone Reference Notebook
The notebook SVclone_Reference_.ipynb provides an example of how downstream analysis is performed for an individual SVclone trial. The output presented in the notebook corresponds to the CN5 with deduplication setting.

The notebook is divided into two main sections:

A. Stacked Bar Chart Generation
This section processes SVclone output by identifying structural variants (SVs) that are shared across all samples. For each sample, the number of SVs classified as clonal or subclonal is counted based on their assigned cluster:

Cluster 2 = clonal

Cluster 1 = subclonal

⚠ Note: When only a single cluster is identified in a sample, all SVs are assigned to cluster 1 by default — this does not necessarily indicate subclonality.
Additionally, in some cases, two distinct clusters may be identified, but both have a mean CCF > 0.7, indicating potential clonal peaks.

This section also counts the number of SVs filtered out under different criteria (e.g., exceeding maximum CN, invalid CN state, etc.).

B. Fisher’s Exact Tests
Fisher’s Exact Tests are applied only to samples where two clusters were identified, to assess whether shared SVs (across all samples) are significantly enriched in the clonal group compared to SVs found in fewer samples.

Heatmap Generation (heatmap_gen.ipynb)
This notebook generates heatmaps to visually compare the performance of different SVclone parameter settings. It takes as input the results from selected Fisher’s Exact Tests, allowing for clear side-by-side comparisons across multiple trial configurations. The heatmaps summarize significance patterns across samples and settings, helping to highlight which configurations yield the most biologically meaningful clustering results.

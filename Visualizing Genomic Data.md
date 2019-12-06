# Genomics 
## Visualizing Genomic Data

**Genomic data** holds the past, present and future of an individual - the human genome. Sequencing the human genome of 3 billion base pairs was not feasible until the development of cheaper and faster sequencing technologies. Now that we can efficiently, and cheaply harvest the data derived from the human genome, how do we visualize its interpretations? 

### Circos Plots
![image.png](https://www.dropbox.com/s/x8cigibubj4ihb1/image.png?dl=0&raw=1)
To visualize genomic data, researchers use **circos plots**; a visualization tool used to identify similarities and differences across the genomic structure. Circos plots can be used to visualize multiple aspects that can be revealed through genomic data; such as chromosome similarity, and phylogeny.  In a circular ideogram layout, circos displays the relationship between positions by the use of ribbons (lines connecting the two points in the circle) that encode position, size and orientation of related genomic sequences. The circlular composition is used to show connections between objects and between positions; connections between neighboring points in the circle indicate close interactions, while farther points indicate distant interactions. 
![circos_connection.png](http://circos.ca/intro/circular_approach/img/circos-ucsc.png)
![type_of_data.png](https://miro.medium.com/max/4152/1*5LvkBQwcRPECEWKDtJO_8g.png)
Circos plots can be made using the original circos software written in Perl, or various R packages, such as:
* cirlize
* RCircos
* CIRCUS
* OmicCircos 

For chromosome visualization, Circa can be used to create the circos plots without any code. 

Although, a seemingly digestable data visualization tool (and pretty too!), data can quicly become convoluted. Circos plots are most effective when there is not too much data crammed in - which can often happen in chromosome-based circos plots. Stay away from adding 20 datasets, with multiple colors and tiny datapoint captions. Ensure that you only highlight the patterns that are interesting rather than all the data you have. 

### Summary:
* Circos plots are a useful and beautiful tool to visualize genomic data
* Points on circumference indicate positions on chromosome, where connections symbolize relationships
* Keep plots simple! Use circos plots to highlight interesting patterns, and not all your data. 

#### Citations
[1] https://genome.cshlp.org/content/early/2009/06/15/gr.092759.109.abstract
[2] https://medium.com/@Marianattestad/a-treatise-on-making-circos-plots-from-genomic-data-7ff496849e0
[3] http://circos.ca/intro/circular_approach/

# RNA-Sequencing 
## Visualizing Expression Data
**Gene expression** is the synthesis of a functional RNA gene product from a gene. Essentially it is the qualification of a phenotype from a genotype. Due to high dimentionality (large number of genes, complexity of biological networks) of the data, it can be difficult to visualize this type of data. In this section, we will explore two data visualization models.

### Principal Component Analysis (PCA)
![PCA.png](https://raybiotech.com/learning-center/wp-content/uploads/2018/11/pca-analysis.png)
Simplifying genomic data like transcriptomes, whole genome sequencing, proteomes, **PCA** is a classical dimension reduction approach where it creates linear combinations of gene expressions, or **principal components**. Principal components are orthogonal to eachother and effectively represent the effects of original measurements by removing redundancies. The purpose of PCA is to reduce dimensionality of the data while preserving as much variance as possible. PCA can be used to discover relationships between biomarkers that can not be easily seen. 
![PCA_2](https://cdn.xlstat.com/media/feature/0001/01/thumb_47_feature_medium.png)
PCA is used when: 
1) there are many variables (expression of thousands of proteins)
2) you want to make sure transformed measurements are independant of eachother

PCA can be ran on excel using [XLSTAT statistical software](https://www.xlstat.com/en/solutions/features/principal-component-analysis-pca), [Analyse-it](https://analyse-it.com/landing/principal-component-analysis-software), among other software. 

### Heatmaps
![heatmap.png](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Heatmap.png/440px-Heatmap.png)
Heatmaps are a data visualization technique that can be used to identify genes that are commonly regulated, find biological signatures, represent changes in gene expression, etc. The colors within the tiles of the heatmap are scaled within a range proportionate to gene expression values (ex, in a range from white=no expression, and black=high expression, dark grey would indicate moderate level of expression and light grey would indicate low level of expression). Gene sequences corrrespond to the row of the martices (n = number genes), and the chips, or samples corrrespond to the columns (n = number samples). Dendrograms flanking the matix depicts clustering/relationships between the rows/columns. 

![Heatmap_Image2](https://bitesizebio.com/wp-content/uploads/2017/03/1.jpg)
### Summary:
* PCAs can be used to reduce the dimensionality of large gene expression datasets 
* Heatmaps can be used to visualize gene expression patterns
#### Citations
[1] https://academic.oup.com/bib/article/12/6/714/221174
[2] https://academic.oup.com/bioinformatics/article/17/9/763/206456
[3] https://www.xlstat.com/en/solutions/features/principal-component-analysis-pca
[4] https://en.wikipedia.org/wiki/Heat_map
[5] https://bitesizebio.com/34121/show-disparity-gene-expression-heat-map/

# ChIP-sequencing

## Visualizing CHIP-sequencing Data
Chromatin immunoprecipitation, or ChIP, is a method used to identify binding sites or transcription factors within the genomone. **ChIP-sequencing** allows for precise analysis of DNA-protein binding sites using next-gen sequencing (NGS). 

### UCSC Genome Browser
The **UCSC Genome Browser** is a powerful web-based genome browser that consolidates published studies and Encyclopedia of DNA Elements (ENCODE) in one easy to use site. Here you can import your genome, and visualize transciption factor binding sites by alignment. 

![ucsc.png](http://systemsbio.ucsd.edu/course/BENG207/tutorial/images/ucscdisplay.jpg)

File formats for UCSC ChIP-seq:
* (*.bed) - BED files describe a simple region in the genome and  usually used to describe ChIP-Seq peaks.
* (*.wig) - Wiggle files are used to display quantitative information across genomic regions and display read depth from ChIP- or RNA-seq experiments.

### Integrative Genome Viewer (IGV)
**IGV** is a Java based genome viewer that runs locally on your computer. 

### Summary:
* UCSC genome browser is a powerful genome browser that holds a lot of published DNA information, but it can be slow to use as it is web-based, making it an optimal choice for smaller datasets. 
* 
#### Citations
[1] https://www.encodeproject.org/documents/92228d7b-f959-4dcd-94d3-39f5173fd92a/@@download/attachment/UsersMtg-UCSCbrowser.pdf
[2] http://homer.ucsd.edu/homer/basicTutorial/genomeBrowsers.html
[3] http://systemsbio.ucsd.edu/course/BENG207/tutorial/images/ucscdisplay.jpg

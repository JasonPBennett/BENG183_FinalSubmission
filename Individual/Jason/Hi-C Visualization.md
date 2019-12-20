# Chapter 5: Data Visualization

It is not often that a single skill can be universally accepted as a necessity for everyone in a field as broad as bioinformatics. It would be practically impossible to have complete mastery over every aspect of bioinformatics, but skill in data visualization represents an integral part of the bioinformaticians toolbox. Regardless of the types of data you are dealing with, there will come a time where you either choose to visualize your data for personal exploratory reasons, or you must present your data and findings to others. Understanding the nature of your data and the data visualization tools at your disposal can be the difference between creating insightful and clear figures that strengthen your points or creating confusing, obfuscating figures that distance your audience from the point you were trying to make. In this chapter, we will discuss various types of data you may encounter and some good practices to follow as well as common pitfalls that you want to be wary of.

# Hi-C Visualization

## A Summary of Chromosome Conformation Capture (3C)

Chromosome conformation capture is a method to detect interacting segments of chromosomes in a genome. This is accomplished by cross-linking the genome using an agent, usually formaldehyde, to arrest the interacting sections of chromatin in place. These segments are then digested using targeted restriction enzymes and ligated back together for PCR amplification. Sequencing is performed following amplification to see which sections were grouped together. The interacting segments are then found when aligning the segments back to the reference genome, and from there, insight into the nature of their interactions can be further studied [1][2].

<p align="center">
<img width="700" height="700" src="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5845197/bin/13039_2018_368_Fig1_HTML.jpg">
</p>

***Figure 1**: An overview of the various 3C technologies and the steps involved in each.*

## Current State of Chromosome Conformation Capture Technology

Hi-C sequencing is currently one of the most commonly used techniques when investigating chromatin interactions. These interactions are often associated with promoters and enhancer regions on the chromosomes, topologically associated domains (TAD), and other structural chromatin features that may play a part in epigenetic gene expression [3]. Hi-C sequencing allows direct investigations of “all vs. all” segments of the genome. This has been enabled by utilizing next generation sequencing, allowing much larger libraries to be created and assessed. Hi-C presents advantages over prior chromosome conformation capture technologies because of this ability to query all vs. all compared to the limited range of prior technologies. The scope of prior chromosome conformation capture techniques can be seen in the following table (truncated from [2]).



| Hi-C visualization| Hi-Browse| JuiceBox| my5C| 3D Genome Browser| Epigenome Browser| 
|-----------|-----------|-----------|-----------|-----------|-----------|
| Intrachromosomal heat map |✓ |✓ |✓ | | |
| Interchromosomal heat map |✓ |✓ |✓ | | |
| Circular plot |✓ | | | |✓ |
| Rotated local heat map | | | |✓ |✓ |
| Local arc track | | | |✓ |✓ |
| Locus-specific circular plot | | | | |✓ |
| Virtual 4C plot | |✓ |✓ |✓ | |
| Multi-dataset visualizations | |✓ |✓ |✓ |✓ |
| Hi-C signal transformations |✓ |✓ |✓ |✓ | |

## Challenges with Hi-C Data

A common problem within bioinformatics, or any field dealing with data at scale, is deciding how to properly treat your data. Hi-C data is looking at interacting segments of the entire genome, and as such, the amount of data produced for a single Hi-C experiment can be enormous and an incredible amount of variation can be seen between segments. These variations can either be due to noise or they can be biologically significant fluctuations that we want to capture. To distinguish between these possibilities, a few techniques have been developed to aid us in our analysis. They are matrix normalization, which assumes that the read matrix is “balanced” and has equal row and column sums, and an iterative correction technique (ICE) used to correct for bias between counts being placed in certain bins (particularly bins which occur near the diagonal of a correlation matrix) [4]. We will leave it to the reader to investigate these techniques as they are quite involved but suffice it to say that some kind of normalization needs to be performed prior to analysis.

Now that we understand 3C technologies, some of their strengths and weaknesses, and how to prepare our own Hi-C data we can begin to discuss visualization techniques.

## Hi-C Visualization Tools

Fortunately, a great deal of effort has gone into developing Hi-C visualization tools and as such, most Hi-C visualization can be done using prebuilt tools. An excellent article was published that goes into detail about five of the most common tools and this will form the basis of our own study into Hi-C visualization [5]. The table above represents an excerpt from that article, highlighting the five different 3C analysis methods commonly used and their various capabilities. Choosing which tool to use and what kind of visualization to generate can be the key to producing meaningful figures, and in the next section, we will discuss exactly that.

## Hi-C Visuals: Large-Scale Data vs. Investigating Individual Loci

When interested in large-scale interactions, the most common tool to determine correlation between genomic loci should come as no surprise: it’s our old friend, the heatmap! Heatmaps are excellent for finding commonly interacting segments within our Hi-C data and especially so when we’re dealing with data at scale because it affords us a zoomed-out view of all interactions at once. Three of the five tools listed above (Hi-Browse, Juicebox, my5C) can generate these heatmaps for us [5][6]. Examples of these large scale visualization techniques can be seen in the following figure.

<p align="center">
<img width="700" height="700" src="https://media.springernature.com/full/springer-static/image/art:10.1186/s13059-017-1161-y/MediaObjects/13059_2017_1161_Fig1_HTML.gif">
</p>

***Figure 2**: Four different large-scale chromatin interaction visualizations. **a.)** Hi-C interactions across all chromosomes in a kidney sample. The green arrow indicates a highly interacting set of samples **b.)** Visualization of the murine X chromosome **c.)** The murine X visualized using a heatmap with a particular locus highlighted using the green circles seen in the heatmap **d.)** A circle plot generated from the interactions found in the murine X chromosome with the green arrow indicating the locus plotted in the previous heatmap in c [5]*

However, what if we need to look more closely at an individual locus? Trying to identify one particular set of interactions in a heatmap which covers the entire genome would be difficult and more importantly, inefficient. Two other tools presented in the above table (3D Genome Browser, Epigenome Browser) would serve us better when examining small local interactions [5]. Examples of output from the local analysis can be seen in the following figure.

<p align="center">
<img width="650" height="1550" src="https://media.springernature.com/full/springer-static/image/art:10.1186/s13059-017-1161-y/MediaObjects/13059_2017_1161_Fig2_HTML.gif">
</p>

***Figure 3:** Local chromatin interaction visualization techniques. **a.)** A cartoon of a single loop of chromatin joined by two proteins **b.)** The circle plot showing the interacting segments, with the specific area that was indicated using red arrows in **a** again being pointed out in this circle plot **c.)** Using the genome browser to identify promoter/enhancer regions identified by the Hi-C data [5]*

The genome-wide visualizations from above and these local visualizations (along with many other visualizations) can be created using just the five tools we've discussed. It is generally a good idea to begin with large-scale visualizations to get some insight into the quality of your Hi-C data and then, when you're reasonably sure your data looks good, you can dive into more refined local analysis visualizations.

# Hi-C Visualization Discussion

As we have seen, Hi-C sequencing can provide valuable insight into the nature of chromatin interaction and further elucidate the nature of particular segments of the genome. This insight is dependent on the choices we make when determining how to approach our data. While any of the techniques or tools we’ve discussed can help guide us in our analysis, there are certainly some tools that are better suited to particular inquiries, and we hope that as you continue through this chapter you keep that principle in mind!


## Hi-C References:

1. Han, J., Zhang, Z. & Wang, K. 3C and 3C-based techniques: the powerful tools for spatial genome organization deciphering.  _Molecular Cytogenetics_  **11,**  (2018).

2. Li, G.  _et al._  Chromatin Interaction Analysis with Paired-End Tag (ChIA-PET) sequencing technology and application.  _BMC Genomics_  **15,**  (2014).

3. Dixon, J. R.  _et al._  Topological domains in mammalian genomes identified by analysis of chromatin interactions.  _Nature_  **485,**  376–380 (2012).

4. Imakaev, M.  _et al._  Iterative correction of Hi-C data reveals hallmarks of chromosome organization.  _Nature Methods_  **9,**  999–1003 (2012).

5. Yardımcı, G. G. & Noble, W. S. Software tools for visualizing Hi-C data.  _Genome Biology_  (2016). doi:10.1101/086017

6. Lajoie, B. R., Berkum, N. L. V., Sanyal, A. & Dekker, J. My5C: web tools for chromosome conformation capture studies.  _Nature Methods_  **6,**  690–691 (2009).



# Data Visualization Conclusion

Over the course of this chapter, we have explored a range of data visualization techniques. We started with specific tools and tips for distinct data sets which lead to more general guidelines for creating effective figures. The sections that dealt with more specialized tools were intended not only as a simple guide in dealing with that particular type of data, but also as an example of how deep you can go when considering what kind of figures you want to make for your own data. For most of the data that you will deal with, there will already be data visualization tools at your disposal. This means that the most difficult part of presenting your data usually will not be generating the figures, but deciding which kind of figures you want to make! These are the choices that we wanted to focus on. We hope that after reading this chapter, you feel more informed and empowered to make your own impactful figures no matter the kind of data you are working with!

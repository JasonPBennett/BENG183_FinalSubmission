


# Visualizing Metagenomic Data
**Phinch** is a data visualization tool that’s used to quickly analyze complex genomic datasets. Phinch is used primarily for metagenomic datasets, and is used to determine the composition of species in these particular datasets. Phinch has several visualizations for datasets that are publication-ready. One visualization is the **taxonomy bar chart**, which allows users to see the abundance of certain taxa in each sample. Another chart that can be used is the **bubble chart**, where the circle size is positively correlated with the abundance of a given taxon. Additionally, Phinch is capable of displaying a **sankey diagram**, which organizes taxa abundance in samples hierarchically by taxonomy. Phinch is a neat tool that can be used to take a glance at your data without the need for heavy programming knowledge.



<p align="center">
  <img width="460" height="300" src="https://lh3.googleusercontent.com/XPB3iYMKCMYYeFmzNfZVNPJIujvALAXPNjz6PLqdk3MK0Fht1vDr6_Rin9MlU6bwS1RK1zEkKEg">
</p>
<p align="center">
  <b>Figure 1</b> a taxonomy bar chart for the abundance of taxa in a coral pond

</p>

<br><br>


<p align="center">
  <img width="460" height="400" src="https://lh3.googleusercontent.com/TEkRPntl3uWbGQr6QIrno25ChirvIAz1PxFN3oblVUsEoJye37gLDDXIDUvCY94LIaZzm23DPWE">
</p>
<p align="center">
  <b>Figure 2</b> a bubble chart for the abundance of taxa in a coral pond

</p>
<br><br>



<p align="center">
  <img width="460" height="400" src="https://lh3.googleusercontent.com/vMTxhrLUlfh_rymkxqKB_bwoMuXJf8pS8PEmeBbTcmc2P7869VE8yDTbEmNCGeXDZgTmghdJ_sU">
</p>
<p align="center">
  <b>Figure 3</b> a sankey chart for the abundance of taxa in a coral pond

</p>


# What Plots Should I Use?
To communicate your research effectively, one must consider how you present your data to others. Graphs are a great way to visualize your data, but how do you know what kind of graph to use? Here is a comparison of the different types of graphs you can use and how they’re useful in different situations.
![
](https://lh3.googleusercontent.com/_jnw5gSxkfYlko_HrB5NdVjPeS5V5JYBH4PSC1MhEaFGCnmhmlfUDinItA0pQAf_A4deZ_KCsaI "plot")
It’s also important to choose a graph that represents your data well. 

For example, a bar graph is more visually appealing in this plot describing cancer incidence than a line plot, because you can see the difference between types more clearly in the bar graph. 

Additionally, it’s very important to order your data in a way that has a logical order, so that trends in the data are obviously seen at first glance. In plotting cancer incidence by tissue type, it’s difficult to see which tissue type has the highest/lowest cancer incidence in the left plot, whereas in the right plot, you can easily see the trend as the types are arranged from highest to lowest cancer incidence.
![
](https://lh3.googleusercontent.com/ntJ2JuZm0BQgaZt-aDpuIEeUAW2Qk8q_IjPr-wcEN_vd9-j3diQ6qwt8PPwoAYpLgsKaNqNhAWg "cancer")


# Choosing Colors that Represent your Data

Although it seems like a minute detail in presenting your data, picking colors is something that cannot be overlooked. To represent your data well, you need to make sure to pick colors that correspond to trends in the data you are trying to emphasize to the reader. **Don’t handpick your colors!** Let the color palettes you pick explain your data. ColorBrewer is a useful tool you can use to pick color schemes for different purposes. The three types of schemes are sequential, diverging, and qualitative. Below are examples of how you could use each color scheme.
![
](https://lh3.googleusercontent.com/RZwcFGaEL_6NI89unqBFINgKY3yW2OjKk5r11Riw4RQN2x9rq-pTgT1jRIjaaOgr_c982Pc86Xw "map")

**Sequential** color schemes imply order and are suited to representing data that ranges from low-to-high values either on an ordinal scale (e.g. cold, warm, hot) or on a numerical scale (e.g. age classes of 0–9, 10–19, 20–29, etc.). For example, to visualize interaction frequency in Hi-C data, one can use this kind of color scheme.
![
](https://lh3.googleusercontent.com/yvrW38gs4jS6M60ujVL-HsGlvLP114p-UHLAjagQbg1dSdPf291EFU6cYHqazKMwZ4f7zjF9nXg "seq")
**Diverging** color schemes should be used when a critical data class or break point needs to be emphasized, particularly if there are two vastly different trends that need to be visualized. For example, to visualize over and underexpression of particular genes for RNA-seq heatmaps, one can use this color scheme.
![
](https://lh3.googleusercontent.com/tfT9KtobwpHUw_sifdRkn_EXwlyCrVLfs0cHGQBSMEifcBNiyjLhRtfsyQdLFPkYNPto6aRzPeY "heat")
**Qualitative** color schemes are used to differentiate data by kind. Since there is no conceptual ranking in this type of data one these colors aren’t too similar to one another, instead these colors are very distinct from one another. For example, if one wants to differentiate between each chromosome in a Manhattan plot, use this color scheme.

![
](https://lh3.googleusercontent.com/xF27-ZtlbyxDt9of5rwQkZ23F1s36wW2bwS0owxDkP9JoeHbPfGB36XrMen3V-fSjS13mT3tLYE "gwas")







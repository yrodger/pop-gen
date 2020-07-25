#### How to set up and run SNAPP

*Briefly, SNAPP can be used to explore history of population/species divergence using just SNP data. SNAPP’s model builds coalescent trees for each SNP locus independently and then integrates over all possible genealogies to provide estimates of the tree topology and parameters of population divergence times and effective population sizes, scaled by mutation rate.*

Useful materials and manuals:
http://evomics.org/wp-content/uploads/2018/01/BFD-tutorial.pdf
http://evomics.org/learning/population-and-speciation-genomics/2020-population-and-speciation-genomics/species-tree-inference/

Follow instructions detailed on the SNAPP website for downloading the required software https://beast2.blogs.auckland.ac.nz/snapp/

Follow the rough guide to SNAPP for useful explanations and easy instructions on setting up your analysis https://github.com/BEAST2-Dev/SNAPP/releases/download/v1.2.0/SNAPP.pdf. These are extra notes:

**1.**	The SNAPP algorithm assumes that loci are unlinked and evolving under a Wright-Fisher model. The first step will be to remove SNP loci putatively under selection. You can use BAYESCAN to identify and filter out significant FST outliers (see fst-outliers.md in this repository).

**2.**	You will read that SNAPP computation load is exponentially increased by more individuals and groups rather than by number of loci, although this is also a compounding factor. As well as removing significant FST outliers you may want to use a dataset with no missing data to further reduce the number of SNP loci without losing too much important information.

**3.**	It is suggested that you cluster your populations/species into groups based on support from previous population genetic structure analysis, such as STRUCTURE or PCoA. Ideally aim for the fewest possible groups that still allow you to explore relationships that you want to test with the software. 

**4.**	Next, you can randomly select a subset of individuals to represent each group. You can do this a further two times to make sure your analysis is not biased by the individuals you chose. Each run should be repeated three times on top of that. Once you have chosen a dataset that is consistent, you can proceed with analysis on the three runs of that particular dataset.

**5.**	If using DArTseq, dartR (R package) has a useful function to convert genlight to NEXUS format, which is required for SNAPP analysis: gl2snapp(). If not using DArTseq but your data is in R as a genind object (adegenet), you can easily convert to genlight gi2gl and then convert to NEXUS.

**6.**	The parameters you choose in BEAUTi to set up your .xml for running through BEAST will depend on your dataset and the extra information you have available, such as mutation rates, etc. If you don’t have any extra information, it is recommended that you use default parameters. Depending on which manual or paper you read, default parameters will differ.  It is important that you state which parameters you used when writing up! 

**7.**	Once you have your NEXUS dataset and .xml parameters file, you should test to see if it begins running on your laptop. This can take some time and if you have chosen a large burn-in, you should check the .log file that is created for evidence of runs. Some help with trouble-shooting may be found here https://groups.google.com/forum/#!forum/beast-users.

**8.**	Now you are ready to run your xml in BEAST! Ideally, you would submit it to a cluster server.

**9.**	Each run will produce a few different files:
.xml.state – this records your run’s progress and will allow you to pause and restart your run from where you left off.
.trees – this is the tree file that you will build your trees from!
.log – this is an important file you will need to examine in Tracer to check for convergence.
Start by looking at your log files in Tracer to see if they converge. You can do this one by one to see if there was a particular run that was unsuccessful or you could combine your log files after you have completed the three replicate runs (suggested). Make sure that your ESS values are >100. Combining your log files can be done in LogCombiner software that comes with the BEAST download. Remember to account for your burn-ins!

**10.**	Once your log files show your run has been successful, you can move on to analyse your trees. Download FigTree (http://tree.bio.ed.ac.uk/software/figtree/) and follow the detailed instructions in the SNAPP-tutorial.pdf.

**11.**	For final graph formatting, I suggest exporting your Densitree graph and then re-drawing your FigTree graph superimposed on this Densitree (I used powerpoint to do this).



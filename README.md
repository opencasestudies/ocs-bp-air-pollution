<!-- README.md is generated from README.Rmd. Please edit that file -->

OpenCaseStudies
===============

### Important links

-   HTML:
    <a href="https://www.opencasestudies.org/ocs-bp-air-pollution/" class="uri">https://www.opencasestudies.org/ocs-bp-air-pollution/</a>
-   GitHub:
    <a href="https://github.com/opencasestudies/ocs-bp-air-pollution/" class="uri">https://github.com/opencasestudies/ocs-bp-air-pollution/</a>
-   Bloomberg American Health Initiative:
    <a href="https://americanhealth.jhu.edu/open-case-studies" class="uri">https://americanhealth.jhu.edu/open-case-studies</a>

### Disclaimer

The purpose of the [Open Case Studies](https://www.opencasestudies.org)
project is **to demonstrate the use of various data science methods,
tools, and software in the context of messy, real-world data**. A given
case study does not cover all aspects of the research process, is not
claiming to be the most appropriate way to analyze a given dataset, and
should not be used in the context of making policy decisions without
external consultation from scientific experts.

### License

This case study is part of the
[OpenCaseStudies](https://www.opencasestudies.org) project. This work is
licensed under the Creative Commons Attribution-NonCommercial 3.0 ([CC
BY-NC 3.0](https://creativecommons.org/licenses/by-nc/3.0/us/)) United
States License.

### Citation

To cite this case study please use:

Wright, Carrie and Jager, Leah and Taub, Margaret and Hicks, Stephanie.
(2020). <https://github.com//opencasestudies/ocs-bp-air-pollution>.
Predicting Annual Air Pollution (Version v1.0.0).

### Acknowledgments

We would like to acknowledge [Roger
Peng](http://www.biostat.jhsph.edu/~rpeng/), [Megan
Latshaw](https://www.jhsph.edu/faculty/directory/profile/1708/megan-weil-latshaw),
and [Kirsten
Koehler](https://www.jhsph.edu/faculty/directory/profile/2928/kirsten-koehler)
for assisting in framing the major direction of the case study.

We would also like to acknowledge the [Bloomberg American Health
Initiative](https://americanhealth.jhu.edu/) for funding this work.

### Title

Predicting Annual Air Pollution

### Motivation

Machine learning methods have been used to predict air pollution levels
when traditional monitoring systems are not available in a particular
area or when there is not enough spatial granularity with current
monitoring systems.

We will use machine learning methods to predict annual air pollution
levels spatially within the US based on data about population density,
urbanization, road density, as well as, satellite pollution data and
chemical modeling data.

### Motivating question

1.  Can we predict annual average air pollution concentrations at the
    granularity of zip code regional levels using predictors such as
    data about population density, urbanization, road density, as well
    as, satellite pollution data and chemical modeling data?

### Data

The data that we will use in this case study come from a
**<a href="https://publiclab.org/wiki/filter-pm" target="_blank">gravimetric air pollution monitor system</a>**
operated by the US
<a href="https://www.epa.gov/" target="_blank">Enivornmental Protection Agency (EPA)</a>
that measures fine particulate matter (PM<sub>2.5</sub>) in the United
States (US). We will use data from 876 gravimetric monitors in in the
contiguous US in 2008.

Roughly 90% of these monitors are located within cities.

Hence, there is an **equity issue** in terms of capturing the air
pollution levels of more rural areas. To get a better sense of the
pollution exposures for the individuals living in these areas, methods
like machine learning can be useful to estimate or predict air pollution
levels in **areas with little to no monitoring**.

We will use data related to population density, urbanization, road
density, as well as, NASA satellite pollution data and chemical modeling
data to predict the monitoring values captured from this air pollution
monitoring system.

The data for these 48 predictors comes from the US
<a href="https://www.epa.gov/" target="_blank">Enivornmental Protection Agency (EPA)</a>,
the
<a href="https://www.nasa.gov/" target="_blank">National Aeronautics and Space Administration (NASA)</a>,
the US
<a href="https://www.census.gov/about/what/census-at-a-glance.html" target="_blank">Census</a>,
and the
<a href="https://www.cdc.gov/nchs/about/index.htm" target="_blank">National Center for Health Statistics (NCHS)</a>.

All of our data was previously collected by a
[researcher](http://www.biostat.jhsph.edu/~rpeng/) at the [Johns Hopkins
School of Public Health](https://www.jhsph.edu/) who studies air
pollution and climate change.

#### Learning Objectives

The skills, methods, and concepts that students will be familiar with by
the end of this case study are:

<u>**Data Science Learning Objectives:**</u>

1.  Familiarity with the tidymodels ecosystem
2.  Ability to evaluate correlation among predictor variables
    (`corrplot` and `GGally`)
3.  Ability to implement tidymodels packages such as `rsample` to split
    the data into training and testing sets as well as cross validation
    sets.
4.  Ability to use the `recipes`, `parsnip`, and `workflows` to train
    and test a linear regression model and random forest model
5.  Demonstrate how to visualize geo-spatial data using `ggplot2`

<u>**Statistical Learning Objectives:**</u>

1.  Basic understanding the utility of machine learning for prediction
    and classification
2.  Understanding of the need for training and test sets
3.  Understanding of the utility of cross validation
4.  Understanding of random forest
5.  How to interpret root mean squared error (rmse) to assess
    performance for prediction

### Analysis

This case study focuses on machine learning methods. We demonstrate how
to train and test a linear regression model and a random forest model.

#### Data import

The data is imported from a CSV file using the `readr` package.

#### Data wrangling

This case study does not demonstrate very many data wrangling methods.
However we do cover the `mutate()` and `across` functions of the `dplyr`
package in the Data wrangling section. In the Data visualzation, some
wrangling was required including combining data using the `inner_join()`
function of the `dplyr` package, using the `separate` function of the
`tidyr` package to make two columns out of one, and the `str_to_title()`
function of the `stringr` package to change the format of some character
strings.

#### Data exploration

We demonstrate how to get a summary of a relatively large set of
predictors using the `skim` package, as well as how to evaluate
correlation among all variables using the `corrplot` package and among
specific variables with more information using the `GGally` package.

#### Statistical concepts

We cover the basics of machine learning: 1) the difference between
prediction and classification 2) the importance of training and testing
3) the concept of cross validation and tuning 4) how random forest works

### Other notes and resources

1.  A review of
    <a href="https://rviews.rstudio.com/2019/06/19/a-gentle-intro-to-tidymodels/" target="_blank">tidymodels</a>  
2.  A
    <a href="https://juliasilge.com/blog/tidymodels-ml-course/" target="_blank">course on tidymodels</a>
    by Julia Silge  
3.  <a href="https://www.tidymodels.org/learn/" target="_blank">More examples, explanations, and info about tidymodels development</a>
    from the developers  
4.  A guide for
    <a href="http://www.rebeccabarter.com/blog/2019-06-06_pre_processing/" target="_blank">pre-processing with recipes</a>  
5.  A
    <a href="https://briatte.github.io/ggcorr/" target="_blank">guide</a>
    for using GGally to create correlation plots  
6.  A
    <a href="https://www.tidyverse.org/blog/2018/11/parsnip-0-0-1/" target="_blank">guide</a>
    for using parsnip to try different algorithms or engines  
7.  A
    <a href="https://tidymodels.github.io/recipes/reference/index.html" target="_blank">list of recipe functions</a>  
8.  A great blog post about
    <a href="https://towardsdatascience.com/train-test-split-and-cross-validation-in-python-80b61beca4b6" target="_blank">cross validation</a>  
9.  A discussion about
    <a href="https://medium.com/@limavallantin/metrics-to-measure-machine-learning-model-performance-e8c963665476" target="_blank">evaluating model performance</a>
    for a deeper explanation about how to evaluate model performance  
10. <a href="https://rstudio.com/resources/cheatsheets/" target="_blank">RStudio cheatsheets</a>
11. An
    <a href="https://towardsdatascience.com/supervised-vs-unsupervised-learning-14f68e32ea8d" target="_blank">explanation</a>
    of supervised vs unsupervised machine learning and bias-variance
    trade-off.
12. A thorough
    <a href="https://royalsocietypublishing.org/doi/10.1098/rsta.2015.0202#:~:text=Principal%20component%20analysis%20(PCA)%20is,variables%20that%20successively%20maximize%20variance." target="_blank">explanation</a>
    of principal component analysis.
13. If you have access, this is a great
    <a href="https://www.tandfonline.com/doi/abs/10.1080/00031305.1984.10483183" target="_blank">discussion</a>
    about the difference between independence, orthogonality, and lack
    of correlation.
14. Great
    <a href="https://youtu.be/_UVHneBUBW0" target="_blank">video explanation</a>
    of PCA.

<u>Terms and concepts covered:</u>

<a href="https://www.tidyverse.org/" target="_blank">Tidyverse</a>  
<a href="https://en.wikipedia.org/wiki/Imputation_(statistics)" target="_blank">Imputation</a>  
<a href="https://en.wikipedia.org/wiki/Data_transformation_(statistics)" target="_blank">Transformation</a>  
<a href="https://en.wikipedia.org/wiki/Discretization_of_continuous_features" target="_blank">Discretization</a>  
<a href="https://en.wikipedia.org/wiki/Dummy_variable_(statistics)" target="_blank">Dummy Variables</a>  
<a href="https://machinelearningmastery.com/why-one-hot-encode-data-in-machine-learning/" target="_blank">One Hot Encoding</a>  
<a href="https://cran.r-project.org/web/packages/hablar/vignettes/convert.html" target="_blank">Data Type Conversions</a>  
<a href="https://statisticsbyjim.com/regression/interaction-effects/" target="_blank">Interaction</a>  
<a href="https://en.wikipedia.org/wiki/Normalization_(statistics)" target="_blank">Normalization</a>  
<a href="https://en.wikipedia.org/wiki/Dimensionality_reduction" target="_blank">Dimensionality Reduction/Signal Extraction</a>  
<a href="https://tartarus.org/gareth/maths/Linear_Algebra/row_operations.pdf" target="_blank">Row Operations</a>  
<a href="https://www.r-bloggers.com/near-zero-variance-predictors-should-we-remove-them/" target="_blank">Near Zero Varaince</a>  
<a href="https://www.datacamp.com/community/tutorials/parameter-optimization-machine-learning-models" target="_blank">Parameters and Hyper-parameters</a>  
<a href="https://towardsdatascience.com/supervised-vs-unsupervised-learning-14f68e32ea8d" target="_blank">Supervised and Unspervised Learning</a>  
<a href="https://medium.com/@savastamirko/pca-a-linear-transformation-f8aacd4eb007" target="_blank">Principal Component Analysis</a>  
<a href="https://www.mathbootcamps.com/linear-combinations-vectors/" target="_blank">Linear Combinations</a>  
<a href="https://medium.com/greyatom/decision-trees-a-simple-way-to-visualize-a-decision-dc506a403aeb" target="_blank">Decision Tree</a>  
<a href="https://towardsdatascience.com/decision-tree-ensembles-bagging-and-boosting-266a8ba60fd9" target="_blank">Random Forest</a>

<u>**Packages used in this case study:** </u>

<table>
<colgroup>
<col style="width: 43%" />
<col style="width: 56%" />
</colgroup>
<thead>
<tr class="header">
<th>Package</th>
<th>Use in this case study</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="https://github.com/jennybc/here_here" target="_blank">here</a></td>
<td>to easily load and save data</td>
</tr>
<tr class="even">
<td><a href="https://readr.tidyverse.org/" target="_blank">readr</a></td>
<td>to import the CSV file data</td>
</tr>
<tr class="odd">
<td><a href="https://dplyr.tidyverse.org/" target="_blank">dplyr</a></td>
<td>to view/arrange/filter/select/compare specific subsets of the data</td>
</tr>
<tr class="even">
<td><a href="https://cran.r-project.org/web/packages/skimr/index.html" target="_blank">skimr</a></td>
<td>to get an overview of data</td>
</tr>
<tr class="odd">
<td><a href="https://cran.r-project.org/web/packages/skimr/index.html" target="_blank">summarytools</a></td>
<td>to get an overview of data in a different style</td>
</tr>
<tr class="even">
<td><a href="https://magrittr.tidyverse.org/articles/magrittr.html" target="_blank">magrittr</a></td>
<td>to use the <code>%&lt;&gt;%</code> pipping operator</td>
</tr>
<tr class="odd">
<td><a href="https://cran.r-project.org/web/packages/corrplot/vignettes/corrplot-intro.html" target="_blank">corrplot</a></td>
<td>to make large correlation plots</td>
</tr>
<tr class="even">
<td><a href="https://cran.r-project.org/web/packages/GGally/GGally.pdf" target="_blank">GGally</a></td>
<td>to make smaller correlation plots</td>
</tr>
<tr class="odd">
<td><a href="https://tidymodels.github.io/rsample/articles/Basics.html" target="_blank">rsample</a></td>
<td>to split the data into testing and training sets and to split the training set for cross-validation</td>
</tr>
<tr class="even">
<td><a href="https://tidymodels.github.io/recipes/" target="_blank">recipes</a></td>
<td>to pre-process data for modeling in a tidy and reproducible way and to extract pre-processed data (major functions are <code>recipe()</code> , <code>prep()</code> and various transformation <code>step_*()</code> functions, as well as <code>bake</code> which extracts pre-processed training data (used to require <code>juice()</code>) and applies recipe preprocessing steps to testing data). See <a href="https://cran.r-project.org/web/packages/recipes/recipes.pdf" target="_blank">here</a> for more info.</td>
</tr>
<tr class="odd">
<td><a href="https://tidymodels.github.io/parsnip/" target="_blank">parsnip</a></td>
<td>an interface to create models (major functions are <code>fit()</code>, <code>set_engine()</code>)</td>
</tr>
<tr class="even">
<td><a href="https://tidymodels.github.io/yardstick/" target="_blank">yardstick</a></td>
<td>to evaluate the performance of models</td>
</tr>
<tr class="odd">
<td><a href="https://www.tidyverse.org/blog/2018/07/broom-0-5-0/" target="_blank">broom</a></td>
<td>to get tidy output for our model fit and performance</td>
</tr>
<tr class="even">
<td><a href="https://ggplot2.tidyverse.org/" target="_blank">ggplot2</a></td>
<td>to make visualizations with multiple layers</td>
</tr>
<tr class="odd">
<td><a href="https://www.tidyverse.org/blog/2019/10/dials-0-0-3/" target="_blank">dials</a></td>
<td>to specify hyper-parameter tuning</td>
</tr>
<tr class="even">
<td><a href="https://tune.tidymodels.org/" target="_blank">tune</a></td>
<td>to perform cross validation, tune hyper-parameters, and get performance metrics</td>
</tr>
<tr class="odd">
<td><a href="https://www.rdocumentation.org/packages/workflows/versions/0.1.1" target="_blank">workflows</a></td>
<td>to create modeling workflow to streamline the modeling process</td>
</tr>
<tr class="even">
<td><a href="https://cran.r-project.org/web/packages/vip/vip.pdf" target="_blank">vip</a></td>
<td>to create variable importance plots</td>
</tr>
<tr class="odd">
<td><a href="https://cran.r-project.org/web/packages/randomForest/randomForest.pdf" target="_blank">randomForest</a></td>
<td>to perform the random forest analysis</td>
</tr>
<tr class="even">
<td><a href="https://cran.r-project.org/web/packages/doParallel/doParallel.pdf">doParallel</a></td>
<td>to fit cross validation samples in parallel</td>
</tr>
<tr class="odd">
<td><a href="https://stringr.tidyverse.org/articles/stringr.html" target="_blank">stringr</a></td>
<td>to manipulate the text the map data</td>
</tr>
<tr class="even">
<td><a href="https://tidyr.tidyverse.org/" target="_blank">tidyr</a></td>
<td>to separate data within a column into multiple columns</td>
</tr>
<tr class="odd">
<td><a href="https://cran.r-project.org/web/packages/rnaturalearth/README.html" target="_blank">rnaturalearth</a></td>
<td>to get the geometry data for the earth to plot the US</td>
</tr>
<tr class="even">
<td><a href="https://cran.r-project.org/web/packages/maps/maps.pdf" target="_blank">maps</a></td>
<td>to get map database data about counties to draw them on our US map</td>
</tr>
<tr class="odd">
<td><a href="https://r-spatial.github.io/sf/" target="_blank">sf</a></td>
<td>to convert the map data into a data frame</td>
</tr>
<tr class="even">
<td><a href="https://cran.r-project.org/web/packages/lwgeom/lwgeom.pdf" target="_blank">lwgeom</a></td>
<td>to use the <code>sf</code> function to convert the map geographical data</td>
</tr>
<tr class="odd">
<td><a href="https://cran.r-project.org/web/packages/rgeos/rgeos.pdf" target="_blank">rgeos</a></td>
<td>to use geometry data</td>
</tr>
<tr class="even">
<td><a href="https://cran.r-project.org/web/packages/patchwork/patchwork.pdf" target="_blank">patchwork</a></td>
<td>to allow plots to be combined</td>
</tr>
</tbody>
</table>

#### For users

There is a [`Makefile`](Makefile) in this folder that allows you to type
`make` to knit the case study contained in the `index.Rmd` to
`index.html` and it will also knit the [`README.Rmd`](README.Rmd) to a
markdown file (`README.md`).

#### For instructors

This case study is intended to introduce fundamental topics in Machine
Learning and to introduce how to implement model prediction using the
tidymodels ecosystem of packages in R.

#### Target audience

This case study is intended for those with some familiarity with linear
regression and R programming.

#### Suggested homework

Students can predict air pollution monitor values using a different
algorithm and provide an explanation for how that algorithm works and
why it may be a good choice for modeling this data.

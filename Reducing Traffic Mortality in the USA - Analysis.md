**1. The raw data files and their format**  
We can open the data set needed for this analysis and by peaking into the types of independent variables and depedent variables provided in the general data sets. 

**2. Read in and get an overview of the data**  
We will peak now closer into the csv road-accidents.csv inside of datasets and obtain general information about this csv.

**3. Create a textual and a graphical summary of the data**  
Summary statistics for the csv is created. A pairplot is also created to  plot the pairwise relationship between each variable in the data set. A few examples would be drvr_fatl_col_bmiles with drvr_fatl_col_bmiles, perc_fatl_speed, perc_fatl_alcohol_, and perc_fatl_1st_time. There are n<sup>2</sup> pairwise graphs given n is the number of variables.

**4. Quantify the association of features and accidents**
Compute the Pearson correlation coefficient matrix which indicates the Pearson correlation coefficient which gives the statistical relationship between two continuous variables. From our data, perc_fatl_alcohol and perc_fatl_speed have the strongest statistical relationship wtih a Pearson correlation coefficient of 0.286244.

**5. Fit a multivariate linear regression**
Compute a multivariate regression model which demonstrates a many-to-one relationship between multiple indenpendent variables to a single dependent variable. The dependent variable is drvr_fatl_col_bmiles. Given the regression coefficients, we see that the linear regression model can be defined as:  
Y = -0.04180041 + 0.19086404x<sub>1</sub> + 0.02473301<sub>2</sub>

**6. Perform PCA on standardized data**  
The data was scaled using StandardScaler such that the mean will be 0 and the standard deviation will be 1. Then, fit_transform() is applied which fits the data and applies the transformation to the set of data. The principal components are the clusters that are highly correlated with each other. The graph demonsrates the proportion of variance explained for each principal component. PC 1 leads in variance explained followed by PC 2. The first two principal components will be focused on. 

**7. Visualize the first two principal components**  
A scatter plot is produced of the first two principal components. This is to visualize the cluster relatinoship (if any) among the three independent variables in the data.There seems to be a weakly negative correlation between the two principals and their independent variables due to the lack of clusters. 

**8. Find clusters of similar states in the data**  
A scree plot is created in hopes of finding clusters within the first two PCs that were not visualized in the scatterplot. In the elbow of the scree plot (the points above the line before the line "flattens"), there are no points hence, no clear elbow exists. 

**9. KMeans to visualize clusters in the PCA scatter plot**  
As there was no clear elbow, we assign the number of clusters to 2-3 and further investigate for clusters with colour-coordination.

**10. Visualize the feature differences between the clusters**  
Each PC is composed of three factors namely, drivers speeding, under alcohol influence, and had not previously been in accident. We can further subdivide each of these clusters by investigating them using a violin plot. Each cluster is represented by a colour split up into the three factors. For each of the clusters, the majourity of accidents seem to be associated with perc_fatl_1st_time (had not previously been in an accident) as many of the violin parts for that category are on the far right. 

**11. Compute the number of accidents within each cluster**  
Data regarding the number of miles in each state will be merged with the pre-existing data as it will help to compute the total number of fatal accidents in each state. The number of fatal accidents per mile is multipled with millions traveled annually in the new data to compute a bar graph with the cluster data and sum statistics. 

**12. Make a decision there is no clear right choice**  
Further investigation needs to be conducted before making any decision regarding new driving policies. However, the cluster that comes to my focus is cluster #2 as the number of total fatal accidents per state was the highest in this cluster and could offer insight regarding the different demographics of fatal accidents and a solution that can stop many of them.


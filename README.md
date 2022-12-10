<h1 id="EMISSION MAPPING FOR MULTISPECIES OF ATMOSPHERIC POLLUTANTS OVER THE CONUS">EMISSION MAPPING FOR MULTISPECIES OF ATMOSPHERIC POLLUTANTS OVER THE CONUS</h1>
<h1 id="by-aashma-acharya">By Aasma Acharya</h1>

<h1 id="introduction">Introduction</h1>

<p>It is significant to track the emissions of harmful gaseous and particulate matter such as NOX, SO2, CO, NH3 and PM2.5 as these pollutants, including greenhouse gasses, are significant climate forcers. The data I am using for my project represents the point source emissions of air pollutants and the climate forcers gasses collected from different inventories over the CONUS and aggregated to extract the final annually averaged emission for the entire CONUS.My CLIM680 project will explore the emission pattern for different species of atmospheric pollutants basically to see how the emission varies spatially within the CONUS. This project will analyze annual total emissions for  NOx, PM2.5,CO, and NH3 measured in terms of ton/km2/yr. This is a qualitative analysis to understand the spatial distriution of anthropogenic emission over the united states.</p>

<p>The most significant and thoroughly investigated air pollutants are ozone, nitrogen dioxide (NO2), and PM2.5 (O3). According to assessments, PM2.5, or particulate matter with a diameter of less than 2.5 m, is one of the main pollutants that cause harmful health impacts.</p>

<h1 id="data">Data</h1>
<p>The datasets used in my project is Neighborhood Emission Mapping Operation (NEMO) dataset:</p>

<p>This data contains annual total emission of VOCs, NOx, PM2.5, SO2, CO, and NH3 by sector in NetCDF format. The anthropogenic emissions in this dataset are generated based on the 2017 National Emissions Inventory (NEI2017) from the US Environmental Protection Agency (US EPA). It has one aggregated emission value for a year over different spatial locations since the NEI only provides aggregate emissions for each county  and the emissions are presented in the unit of ton/km2/year. The emission data are mapped at 1 km spatial gridding and at hourly intervals and the corresponding geo-registration that provides the latitude and longitude is provided by different xarray dataset.The source sector of these emissions are anthropogenic fugitive dust (afdust), agriculture (ag),nonpoint (nonpt), oil and gas operations (np_oilgas), onroad, nonroad, rail, residential wood combustion (rwc), and airports. 
</p>

<p><a href="http://air.csiss.gmu.edu/aq/US01emis/">Link to dataset description</a></p>
<h3 id="regriding(spatial interpolation)"> Regridding(Spatial Interpolation)</h1>
<p>My dataset is in irregular grids with 3177 values of Row and 5397 values of column for the corresponding latitudes and longitudes. This means that the latitudes aren't the same for all longitudes and the longitudes aren't the same for all latitudes. So I have re-gridded my data set at first. I used a bilinear regrid method for this. Bilinear interpolation (grid Method.BILINEAR) calculates the value for the destination point as a combination of multiple linear interpolations, one for each dimension of the Grid. This method is simply linear interpolations, first along the x-axis and then along the y-axis. The weighting for the interpolation is given by the area ratio of the four rectangles splitted by the grid node to their area sum.</p>

<h3 id="spatial variation">Spatial Variation</h3>

<p>I have looked at the contour plots for the dataset to observe the spatial variation of the variables in my dataset to understand how the emission variation is changing with the space. I couldn't include the temporal variation cause the dataset I had is yearly aggregated.</p>

<h3 id="function-creation">Function creation</h3>
 <p>A function was created to regrid the ireggular grids of the dataset and to come up with the spatial distribution representation, labeled as the below mentioned names in the list. This is in addition to the clim680 function generated in class to calculate xyticks.</p>
                         
<p>Xe. Regridder function : I have used one of the ESMF regridding functionality for my dataset.</p>
<p> X-array-dataset.reset.coords: It changes or reset the coordinates into variables. In this project scenario this function is used to change the lat and lon which was under the data variable section to reset them as coordinates.</p>
<p> X-array.DataArray.to_dataset : It basically converts input dataset to time lagged dataset. It is used for converting a DataArray to a DataSet.</p>
<p>Arrange() :  It's the function used to return evenly spaced values within the given interval.</p>
<p>gridlines(): It's simply  used to configure the gridlines.</p>

<p><img src="" alt="Annual averaged emission for the year 2017" /></p>


<h1 id="results-and-analysis">Results and Analysis</h1>
<h3 id="project-notebook-via-github">Project Notebook via Github</h3>
<p>Located within my CLIM680-project repository is a series of jupyter notebooks that contain all of the labeled and commented code that was used in my analysis. 
<a href="https://github.com/aachar52/CLIM680-project/">Link:</a></p>


<h3 id="conda-environment">Conda Environment</h3>
<p>The environment.yml file is shown to define the environment needed to run all code successfully.</p>

<h1 id="references">References</h1>
<p>Archibald, A. T., Folberth, G., Wade, D. C., & Scott, D. (2017). A world avoided: Impacts of changes in anthropogenic emissions on the burden and effects of air pollutants in Europe and North America. Faraday Discussions, 200(0), 475–500. https://doi.org/10.1039/C7FD00004A/</p>

<p>Ma, S., & Tong, D. Q. (2022). Neighborhood Emission Mapping Operation (NEMO): A 1-km anthropogenic emission dataset in the United States. Scientific Data, 9(1), Article 1. https://doi.org/10.1038/s41597-022-01790-9</p>

<p>ESMPy: ESMF Python Regridding Interface. (n.d.). Earth System Modeling Framework. Retrieved December 10, 2022, from https://www.earthsystemmodeling.org/esmpy/</p>

<p>Knight, J. R.,C. K. Folland, and A. A. Scaife (2006), Climate impacts of the Atlantic Multidecadal Oscillation, Geophys. Res. Lett., 33, L17706, doi:10.1029/2006GL026242.</p>

<p>Pedgley, D. E., &amp; Krishnamurti, T. N. (1976). Structure and Behavior of a Monsoon Cyclone over West Africa, Monthly Weather Review, 104(2), 149-167. Retrieved Dec 1, 2021, from https://journals.ametsoc.org/view/journals/mwre/104/2/1520-0493_1976_104_0149_saboam_2_0_co_2.xml</p>

<h1 id="acknowledgements">Acknowledgements</h1>
<p>I would like to thank both the CLIM680 instructors Prof. Dirmeyer and Prof. Burls for coding assistance and answering questions, as well as my advisor Prof. Kinter for dataset selection, project inspiration, and interesting discussions this semester.</p>




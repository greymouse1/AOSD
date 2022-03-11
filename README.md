# AOSD
Final project for Analysis of spatio-temporal data

Nowadays, global warming is taken as an undeniable truth, being confirmed by multiple studies across the globe.[1] Rising temperatures can have negative effects on likelihood of different populations around the world, mainly by affecting conditions for growing foods, disturbing sensitive ecosystems, and rising sea levels. Croatia is consisted of three distinctive parts; continental part, mountainous part and coastal part. Each one of them has different climate and temperatures even though whole country is classified as having continental climate and coast hosting mediteranean climate. We would like to have a sense of how climate change and increasing temperatures affect different parts of Croatia, which can be used as a starting point for more detailed research in order to plan mitigation measures for possible negative effects of increasing temperatures.
With wide availability of sensors which measure atmospheric conditions, we can access data for desired area and inquire on how temperatures affect that area.
In this work, we will look at temperature data recorded on 30 stations on the territory of Republic of Croatia, starting in 2004. and ending in 2020. Data is provided by NOAA (National Oceanic and Atmospheric Administration)[2]. Detailed data with Croatian boundaries is provided by OpenStreetMap. Inspiration was taken from two papers, Spatio-temporal regression kriging model of mean daily temperature for Croatia by Sekulić et al. [3] and Spatio-temporal prediction of daily temperatures using time-series of MODIS LST images by Hengl et al. [4]. In the former paper, authors are using spatio-temporal regression kriging for year 2008., for which they have daily temperature data from two different sources (Global Surface Summary of the Day and Croatian mean daily temperature dataset), and they are adding covariates, namely digital elevation model (DEM) and topographic wetness index (TWI). Authors estimate higher level of uncertainty for higher altitudes and recommend this model only for agricultural areas which are located in low to medium altitudes. Later paper is using in part same data like the former (from national meteorological stations of Croatia, 159 of them) for same year (2008.). In addition to this, temperature is modelled as a function of latitude, longitude, distance from sea, elevation, time, insolation and MODIS LST (Land surface temperature) images. Conclusion is that use of spatio-temporal regression kriging and incorporation of time-series of remote sensing images leads to significantly more accurate maps of temperature compared to using only spatial techniques.
Other work which was used as and aid in writing code and structuring data processing was vignettes for **gstat** and **spacetime** [5][6][7], as well as tutorial on spatio-temporal kriging published by Fabio Veronesi on r-bloggers.com [8]. **spacetime** provides and iddeal way for storing spatio-temporal data in the form of a STFDF object, which acts as a holder of positions (longitude and latitude for measurement stations), time (in my case year instances, but can also be periods of time), and relevant data (average yearly or seasonal readings for each year and each station). **gstat** is package for geo-statistics which has functionality for modelling spatio-temporal variograms, and taking such modelled variogram and STFDF object as input, it can perform kriging for desired area.

In this work, we want to answer the following questions: 

* Is there a trend of rising temperature in Croatia? 
* Which seasons are most affected?
* How are temperatures changing on temporal and spatial scale? 


[1] J. Cook, et al, "Consensus on consensus: a synthesis of consensus estimates on human-caused global warming," Environmental Research Letters Vol. 11 No. 4, (13 April 2016); DOI:10.1088/1748-9326/11/4/048002

[2] NOAA https://www.ncei.noaa.gov

[3] Sekulić, A., Kilibarda, M., Protić, D. et al. Spatio-temporal regression kriging model of mean daily temperature for Croatia. Theor Appl Climatol 140, 101–114 (2020). https://doi.org/10.1007/s00704-019-03077-3

[4] Hengl, T., Heuvelink, G.B.M., Perčec Tadić, M. et al. Spatio-temporal prediction of daily temperatures using time-series of MODIS LST images. Theor Appl Climatol 107, 265–277 (2012). https://doi.org/10.1007/s00704-011-0464-2

[5] Pebesma, Edzer.Spacetime: Spatio-Temporal Data in R. Journal of Statistical Software. 51. 1-30. (2012). 10.18637/jss.v051.i07.

[6] Pebesma, Edzer, Graeler, Ben. Introduction to spatio-temporal variography  (2021.)

[7] Pebesma, Edzer, Graeler, Ben. Gerard Heuvelink. Spatio-temporal interpolation using gstat (2016.) 

[8] Veronesi, Fabio. Spatio-temporal kriging in R (2015.) https://www.r-bloggers.com/2015/08/spatio-temporal-kriging-in-r/

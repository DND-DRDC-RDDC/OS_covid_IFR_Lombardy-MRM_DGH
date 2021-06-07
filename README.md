# covid_IFR_Lombardy-MRM_DGH
Estimating the infection fatality rate of Covid-19 using demographics data and deaths records from Italy's hardest hit area

All code within this repository is published under the MIT license (see LICENSE file).  Original code from https://github.com/gianlucaRinaldi/covid_IFR_Lombardy Copyright (c) 2020 Gianluca Rinaldi. This code was published in relation to https://doi.org/10.1101/2020.04.18.20070912 "An empirical estimate of the infection fatality rate of COVID-19 from the first Italian outbreak" by Gianluca Rinaldi and Matteo Paradisi. 

Additions and alterations made by Matthew R. MacLeod are Copyright (c) Her Majesty the Queen in Right of Canada, Department of National Defence, 2021. The additional code and alterations are published in support of Matthew R. MacLeod, D. Gregory Hunter, "The Impact of Age Demographics on Interpreting and Applying Population-Wide Infection Fatality Rates for COVID-19," INFORMS Journal on Applied Analytics (Vol. 51, No. 3)  https://doi.org/10.1287/inte.2020.1070.

If using a Mac, rjags installation might not work immediately: please download and install JAGS from 
https://sourceforge.net/projects/mcmc-jags/files/JAGS/4.x/Mac%20OS%20X/ 
and then run "main.R" again.

To replicate the exhibits in the Rinaldi and Paradisi paper, please set the working directory of the local downloaded project in "main.R" and then run it.  This will will store the input for tables 1 and 2 is in the workspace as data.table objects table1Data and table2Data, which are required to run the MacLeod and Hunter code.

The original codebase from https://github.com/gianlucaRinaldi/covid_IFR_Lombardy contained a brief file entitled "oecdComparison.R" run by "main.R" that generates IFR estimates for OECD countries and plots in the file "IFRbyCountry.pdf", although this was not included in the Rinaldi and Paradisi pre-print. The MacLeod code extended this code in multiple directions to e.g., consider the estimated IFR of sub-national populations in Canada, and also incorporate IFR estimates from multiple other published studies on other source populations.

"code/oecdComparison.R" will be run by "main.R", or can be re-run on its own after "main.R" is run to e.g., vary the figure options.  It produces Figures 1, 2 and 4 from the MacLeod and Hunter paper.  Its main purpose as used in that analysis is to compare the sum of weighted quantiles methods with the quantiles of a weighted sum.  

"code/oecdComparisonMRM.R" must be run separately after "main.R", and produced Figures 3, 5 and 6 from the MacLeod and Hunter paper. These figures compare the different infection fatality rates (IFR) generated from multiple source papers applied to different populations and age bands.

Note that the Canadian population values in "data/canInterim.csv" and "data/caninterim10.csv" were initially based on interim population estimates that have since been adjusted to final totals, so do not exactly the values currently found at Statistics Canada, Table 17-10-0005-01: Population estimates on July 1st, by age and sex. Accessed May 28, 2020, http://dx.doi.org/https://doi.org/10.25318/1710000501-eng. The demographic share values for the Canadian Armed Forces (CAF) in the table are rounded from the exact totals used in the published analysis, and exact population figures are not included. 


IFR estimates in "data/ifrVeritySalje.csv" are taken from "Verity R, Okell LC, Dorigatti I, Winskill P, Whittaker C, Imai N, Cuomo-Dannenburg G, et al. (2020a) Estimates of the severity of coronavirus disease 2019: A model-based analysis. Lancet Infectious Diseases 20(6):669–677" and "Salje H, Tran Kiem C, Lefrancq N, Courtejoie N, Bosetti P, Paireau J, Andronico A, et al. (2020a) Estimating the burden of SARS-CoV-2 in France. Science 369(6500):208–211" (as well as its revision).

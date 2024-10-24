# Project I: Analysis of Meteorological Data from the ISD NOAA Database

## 1. Objective

The aim of this project is to familiarize students with working on "encoded" data files, which are stored using alphanumeric characters, without column delimiters or headers. The data used is raw, and the task requires understanding the data format, learning tools to facilitate processing, and performing statistical analysis to identify trends and correlations between the variables. Finally, a technical report was written using **RMarkdown** to document the work performed in **R**.

## 2. R (Programming Language)

**R** is an interpreted programming language and an environment for statistical computations. It is widely used for the analysis of environmental and spatial data and their visualization. R is similar to the S language developed at Bell Laboratories by John Chambers and others, and it has been implemented by Robert Gentleman and Ross Ihaka at the University of Auckland. R is excellent for interactive data work as it combines functional and object-oriented programming features.

*For more information, see [R on Wikipedia](https://en.wikipedia.org/wiki/R_(programming_language))*

## 3. R Markdown

**R Markdown** is a file format for creating dynamic documents using R. An R Markdown file is written in a way that makes editing text simple, with easy embedding of code chunks that execute **R** commands. **R Markdown** is a convenient tool for formatting HTML, PDF, and MS Word documents.

*For more information, see [R Markdown Overview](https://rmarkdown.rstudio.com/articles_intro.html)*

## 4. ISD NOAA Database

The [ISD NOAA](https://www.ncdc.noaa.gov/isd) (Integrated Surface Database of the National Oceanic and Atmospheric Administration) is one of the largest collections of freely available meteorological data. It contains hourly averages from 12,826 ground observation stations worldwide.

Meteorological data in ASCII format is available via [FTP](ftp://ftp.ncdc.noaa.gov/pub/data/noaa), though downloading it manually is laborious. The data format requires preprocessing before it can be analyzed freely. The ISH (Integrated Surface Hourly) file format documentation contains detailed information about the available variables and their units. Each line of the file is a coded sequence of numbers and letters, and understanding its exact structure is necessary for accurate analysis.

Key variables include meteorological measurements, station and observation source data, as well as quality control test results.

*For more information, see [ISH Format Documentation](ftp://ftp.ncdc.noaa.gov/pub/data/ish/ish-format-document.pdf)*

## 5. Selected Station: Tokyo

For this project, we used the station "TOKYO" located in the heart of Japan's capital.

```r
getMeta(site = "TOKYO", lat = 35.6833333333, lon = 139.76666666666668, end.year = "current", plot = T, returnMap = T )

# Assign station data
Japan <- getMeta(site = "TOKYO", lat = 35.6833333333, lon = 139.76666666666668, end.year = "current", plot = T, returnMap = T )

# Import data from selected station
Tokyo <- importNOAA(code = '476620-99999', year = 1952:2020)
```
Tokyo is one of the largest metropolises globally, consisting of 23 cities and towns. It has very little green space per capita and is highly organized and expensive. The station in Tokyo has been operational since 1952, with a brief data interruption in 2005. The most accurate and continuous data was recorded between 2006 and 2020, with approximately 9,000 annual data points, close to the theoretical 8,750.

For detailed analysis, we chose the period 2006–2016, as it provided the most accurate and continuous data.
![Ciągłość_Obserwacji-1](https://github.com/user-attachments/assets/1694e87a-79e1-4340-820f-4bde26548916)

## Screenshot
![histogram_4_pory-1](https://github.com/user-attachments/assets/6584362a-9aaf-4454-9118-bfcf395f4d76)
![Trend_all-1](https://github.com/user-attachments/assets/49797231-a2a3-43ae-bc35-80a008a4f687)
![Wykresy_rozrzutu-1](https://github.com/user-attachments/assets/a9944bc7-608f-4ca8-8fd8-3b32648d4bd4)
![Wykres_rozrzutu_z_trzecia_zmienna-1](https://github.com/user-attachments/assets/88ea3308-3f12-4f07-a6c2-ebcb7c620926)

## Conclusion

In conclusion, this project enhanced our knowledge of meteorological data analysis and the ISD NOAA database. We explored multiple methods for processing and analyzing such data using the R programming language. By gaining experience with RStudio and statistical analysis techniques, we are well-prepared to apply these skills to future tasks, achieving precise and efficient results. The most significant aspect of this project was learning how to conduct statistical analysis with R.

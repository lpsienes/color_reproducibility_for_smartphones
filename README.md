# Color reproducibility for smartphones

![image (2)](https://user-images.githubusercontent.com/102466458/160293696-27c1b33d-35d0-4a08-823e-1acd7b894274.jpg)

<p align="justify">This repository shows the algorithm and methodology implemented on the scientific article:[*Titulo*](). Python® programming language was used in order to develop this algorithm. Its main purpose is to fit the differences between the RGB measurements of a device with their counterpart RGB referenced color gamut so it can be applied to (bio)chemical quantitative determinations, making the measurements comparable between devices.</p> 

- [Getting Started](Getting-Started)
- [Estructure of the program](#Estructure-of-the-program)
- [References](#References)
- [Link to Binder](#Link-to-Binder)

# Getting Started

<p align="justify">In a (bio)chemical quantitative determination, a certain concentration of dye dispersed or dissolved in a specific support (cellulose sheet, paper strips, etc) is associated with a specific color, since it corresponds to a specific concentration of dye, that is, an RGB value. Therefore, any chemical or biochemical colorimetric reaction can be traced with any device capable of taking a digital image[1,2]. However, as our own experience has suggested in various experiments [3-5], digital image colorimetry (DIC) is subjected to a series of variables [6] such as: intensity of the light source used for the measurements, type of illuminant, devices sensor, etc. All of these variables make the color measurements not comparable among different devices and induce to systematical errors. That is why all the possibilities of the DIC for color-based control tests have not yet been exploited.</p> 

<p align="justify">What is intended with this program is to solve some of this problems in order make color measurements between digital devices comparable,applying color theory for these corrections[7,8]. To do so, a simple Python® code will generate two matrices so the color values given by the device and the referenced ones can be adjust by means of lineal regression, correcting the measurement through the standardization of the light wave composition of the light source used and its intensity.This program is intended to be used with JPEG image format, which uses sRGB color space, and D65 as the reference illuminant but it can be used in any image format with any illuminant as long the RGB reference values are well known.</p> 

<p align="justify">To work with this program, two csv files are necessary: one with the referenced RGB values of the samples and another with the RGB measurements taken with our device.Once the files are uploaded, all you have to do is run the code and collect the data (Make sure that each sample corresponds to the reference values and that there are the same number of samples in both csvs).</p> 


# Estructure of the program

<p align="justify">The first part of the program is focused on the comparision of the devices measurements with the reference ones. The RGB values of both csv archives will be shown as so:</p> 

||Measurements||References|
|:-:|:-: |:-:|:-:|
|<table><tr><td>n</td></tr><tr><td>0</td></tr><tr><td>1</td></tr><tr><td>2</td></tr><tr><td>3</td></tr><tr><td>4</td></tr><tr><td>...</td></tr></table>|<table> <tr><th>R</th><th>G</th><th>B</th></tr><tr><td>151</td><td>159</td><td>83</td></tr><tr><td>159</td><td>144</td><td>85</td></tr><tr><td>157</td><td>141</td><td>54</td></tr><tr><td>171</td><td>172</td><td>151</td></tr><tr><td>133</td><td>125</td><td>96</td></tr><tr><td>...</td><td>...</td><td>...</td></tr></table>|<table><tr><td>n</td></tr><tr><td>0</td></tr><tr><td>1</td></tr><tr><td>2</td></tr><tr><td>3</td></tr><tr><td>4</td></tr><tr><td>...</td></tr></table>|<table><tr><th>R</th><th>G</th><th>B</th></tr><tr><td>202</td><td>182</td><td>128</td></tr><tr><td>204</td><td>172</td><td>126</td></tr><tr><td>207</td><td>166</td><td>105</td></tr><tr><td>228</td><td>208</td><td>178</td></tr><tr><td>163</td><td>140</td><td>116</td></tr><tr><td>...</td><td>...</td><td>...</td></tr></table>|

<p align="justify">After these, the error between the RGB measurement values and the reference in each RGB channel independently will be displayed:</p> 

|R Channel Error|Green Channel Error|Blue Channel Error|
|:-:|:-: |:-:|
|<table><tr><td>![3](https://user-images.githubusercontent.com/102466458/160297824-75edef19-7dc1-403d-aa82-e13a1f1de4d1.jpg)</td></table>|<table><tr><td>![4](https://user-images.githubusercontent.com/102466458/160297839-563a5771-da71-4445-a170-f79d2979bccf.jpg)</td></table>|<table><tr><td>![5](https://user-images.githubusercontent.com/102466458/160297853-cb1f5e14-0645-4630-afeb-d5e9bfe1a3e8.jpg)</td></table>|



<p align="justify">The second part of the program is centered on the correction of the devices RGB values.First, the program generates two matrices to adjust the color values given by the device to the referenced ones by means of lineal regression, correcting the measurement through the standardization of the light wave composition of the light source used and its intensity. The correlation factor of the new RGB values and the referenced ones it is also displayed:</p> 

|Correction Matrices||Corrected|
|:-:|:-:|:-:|
|<table><tr><td>![3](https://user-images.githubusercontent.com/102466458/160299029-70d6de61-ce08-440c-a603-23189d454407.jpg)</td></table>|<table><tr><td>n</td></tr><tr><td>0</td></tr><tr><td>1</td></tr><tr><td>2</td></tr><tr><td>3</td></tr><tr><td>4</td></tr><tr><td>...</td></tr></table>|<table><tr><th>R</th><th>G</th><th>B</th></tr><tr><td>151</td><td>159</td><td>83</td></tr><tr><td>159</td><td>144</td><td>85</td></tr><tr><td>157</td><td>141</td><td>54</td></tr><tr><td>171</td><td>172</td><td>151</td></tr><tr><td>133</td><td>125</td><td>96</td></tr><tr><td>...</td><td>...</td><td>...</td></tr></table>|















<p align="justify">Then, three plots of the RGB values (Sample, Reference and Prediction) will be displayer on the RGB color space:</p> 

![9](https://user-images.githubusercontent.com/102466458/160299738-2193fc7b-82c9-4819-934e-6dcbe978061b.jpg)![10](https://user-images.githubusercontent.com/102466458/160299741-c3fc78e0-7491-4964-bda1-58947ab40856.jpg)![11](https://user-images.githubusercontent.com/102466458/160299743-d1d4610a-9ccf-4e1b-9f29-3e5a2f7dd80f.jpg)

<p align="justify">The last part of the program includes the option to calculate the correlated color temperature (CCT) of a sample introducing its CIE XYZ manually.  The CCT is a measure of light source color appearance defined by the proximity of the light source's chromaticity coordinates to the blackbody locus, as a single number rather than the two required to specify a chromaticity. This method was described and developed by A. R. Robertson [9]. The correlated color temperature is usually represented in the CIE xy color space as shown in the next figure:</p> 

![12](https://user-images.githubusercontent.com/102466458/160299846-cd657cf7-d5da-496e-b0ac-0bc6277f5db6.jpg)

<p align="left">
  <img 
    width="400"
    height="400"
    src="https://user-images.githubusercontent.com/102466458/160288160-07edd717-50d3-40f8-9250-0d6dd6dbf4d5.gif"
  >
</p>

# References
1. Quesada-González, D., & Merkoçi, A. (2017). Mobile phone-based biosensing: An emerging “diagnostic and communication” technology. Biosensors and Bioelectronics, 92, 549-562.
2. Kim, J., Leksikov, S., Thamjamrassri, P., Lee, U., & Suk, H. J. (2015, August). Crowdcolor: Crowdsourcing color perceptions using mobile devices. In Proceedings of the 17th International Conference on Human-Computer Interaction with Mobile Devices and Services (pp. 478-483)
3. De Marcos, S., Sanz-Vicente, I., López-Molinero, Á., Camacho-Aguayo,J., Dominguez, M., Cebrián, P., Navarro,. J., Martín-Barreiro, A. & Galbán, J. (2021). Enzymatic biosensors based on in-situ generation of gold nanomaterials: an alternative to classic enzymatic methods. Available online: https://www.seqa.es/ActualidadAnalitica/AA_75/015.pdf (accessed on 1 March 2022).
4. Oliver, S., de Marcos, S., Sanz-Vicente, I., Cebolla, V., & Galbán, J. (2021). Direct minimally invasive enzymatic determination of tyramine in cheese using digital imaging. Analytica Chimica Acta, 1164, 338489.
5. Sanz-Vicente, I., López-Molinero, Á., de Marcos, S., Navarro, J., Cebrián, P., Arruego, C., ... & Galbán, J. (2020). Smartphone-interrogated test supports for the enzymatic determination of putrescine and cadaverine in food. Analytical and bioanalytical chemistry, 412, 4261-4271.
6. Fan, Y., Li, J., Guo, Y., Xie, L., & Zhang, G. (2021). Digital image colorimetry on smartphone for chemical analysis: A re-view. Measurement, 171, 108829.
7. International Color Consortium. (2004). Image technology colour management-Architecture, profile format, and data structure. Specification ICC. 1: 2004-10 (Profile version 4.2. 0.0).
8.	Wyszecki, G., & Stiles, W. S. (1982). Color science: Concepts and Methods, Quantitative Data and Formulae (Second Edition). New York: Wiley.11-27,51-66,83-93,119-154,429-439.
9.Robertson, A. R. (1968). Computation of correlated color temperature and distribution temperature. JOSA, 58(11), 1528-1535.

# Link to Binder
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/lpsienes/color_reproducibility_for_smartphones/main)

# Color reproducibility for smartphones

<img width="650" alt="logos" src="https://user-images.githubusercontent.com/102466458/210554478-8c9354cf-ac65-41ac-a1d8-1b9d7b83bdd7.PNG">

![image (2)](https://user-images.githubusercontent.com/102466458/160293696-27c1b33d-35d0-4a08-823e-1acd7b894274.jpg)

<p align="justify">This repository shows the algorithm and methodology implemented on the scientific article:

[Solving Color Reproducibility between Digital Devices: A Robust Approach of Smartphones Color Management for Chemical (Bio)Sensors](https://www.mdpi.com/2079-6374/12/5/341).

Python® programming language was used in order to develop this algorithm. Its main purpose is to fit the differences between the RGB measurements of a device with their counterpart RGB referenced color gamut so it can be applied to (bio)chemical quantitative determinations, making the measurements comparable between devices.</p>

- [Getting Started](#Getting-Started)
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
|<table><tr><td>n</td></tr><tr><td>0</td></tr><tr><td>1</td></tr><tr><td>2</td></tr><tr><td>3</td></tr><tr><td>4</td></tr><tr><td>...</td></tr></table>|<table> <tr><th>R</th><th>G</th><th>B</th></tr><tr><td>151 </td><td>159</td><td>83</td></tr><tr><td>159</td><td>144</td><td>85</td></tr><tr><td>157</td><td>141</td><td>55</td></tr><tr><td>171</td><td>172</td><td>151</td></tr><tr><td>134</td><td>125</td><td>96</td></tr><tr><td>...</td><td>...</td><td>...</td></tr></table>|<table><tr><td>n</td></tr><tr><td>0</td></tr><tr><td>1</td></tr><tr><td>2</td></tr><tr><td>3</td></tr><tr><td>4</td></tr><tr><td>...</td></tr></table>|<table><tr><th>R</th><th>G</th><th>B</th></tr><tr><td>202</td><td>182</td><td>128</td></tr><tr><td>204</td><td>172</td><td>126</td></tr><tr><td>207</td><td>166</td><td>105</td></tr><tr><td>228</td><td>208</td><td>178</td></tr><tr><td>163</td><td>140</td><td>116</td></tr><tr><td>...</td><td>...</td><td>...</td></tr></table>|

<p align="justify">After these, the error between the RGB measurement values and the reference in each RGB channel independently will be displayed:</p> 

![3](https://user-images.githubusercontent.com/102466458/160783791-3e090645-a051-4f7f-94a9-36255ac59401.jpg)![4](https://user-images.githubusercontent.com/102466458/160783988-675c4875-5605-47f9-9f32-2b2cace88200.jpg)![5](https://user-images.githubusercontent.com/102466458/160784053-f97eb5ba-6559-470f-b63e-aae8099919da.jpg)

<p align="justify">The second part of the program is centered on the correction of the devices RGB values.First, the program generates two matrices to adjust the color values given by the device to the referenced ones by means of lineal regression, correcting the measurement through the standardization of the light wave composition of the light source used and its intensity. The correlation factor of the new RGB values and the referenced ones it is also displayed:</p> 


|Correction Matrices||Corrected|
|:-:|:-:|:-:|
|<table><tr><td>![6](https://user-images.githubusercontent.com/102466458/160783461-150c91b7-9551-4464-b628-6685be5a269a.jpg)</td></table>|<table><tr><td>n</td></tr><tr><td>0</td></tr><tr><td>1</td></tr><tr><td>2</td></tr><tr><td>3</td></tr><tr><td>4</td></tr><tr><td>...</td></tr></table>|<table><tr><th>R</th><th>G</th><th>B</th></tr><tr><td>190</td><td>168</td><td>112</td></tr><tr><td>192</td><td>155</td><td>111</td></tr><tr><td>192</td><td>148</td><td>88</td></tr><tr><td>208</td><td>191</td><td>166</td></tr><tr><td>161</td><td>137</td><td>111</td></tr><tr><td>...</td><td>...</td><td>...</td></tr></table>|


<p align="justify">Then, three plots of the RGB values (Sample, Reference and Prediction) will be displayer on the RGB color space:</p> 

![8](https://user-images.githubusercontent.com/102466458/160366554-2f19f0dd-6288-41be-afa4-c3cf566cc259.jpg)![9](https://user-images.githubusercontent.com/102466458/160366537-7a18af38-dbbb-41e4-b75c-2b7e4796f9ea.jpg)![10](https://user-images.githubusercontent.com/102466458/160366581-83f2d041-4a86-4825-b950-23196cd51574.jpg)

<p align="justify">After these, the error between the Prediction RGB measurement values and the reference in each RGB channel independently will be displayed:</p>


![11](https://user-images.githubusercontent.com/102466458/160784860-709f4453-92ec-4021-beed-00d95709761b.jpg)![12](https://user-images.githubusercontent.com/102466458/160784871-404c93b4-9918-48c6-a452-a94d487ec40b.jpg)![13](https://user-images.githubusercontent.com/102466458/160784876-44bd2bea-267b-4e6d-ac65-b76905a4fd1e.jpg)

<p align="justify">The last part of the program includes the option to calculate the correlated color temperature (CCT) of a sample introducing its CIE XYZ manually.  The CCT is a measure of light source color appearance defined by the proximity of the light source's chromaticity coordinates to the blackbody locus, as a single number rather than the two required to specify a chromaticity. This method was described and developed by A. R. Robertson [9]. The correlated color temperature is usually represented in the CIE xy color space as shown in the next figure:</p> 

![14](https://user-images.githubusercontent.com/102466458/160366713-3be869b6-1b8c-4a1f-94ab-dfe9044c7cfd.jpg)

<p align="left">
  <img 
    width="400"
    height="400"
    src="https://user-images.githubusercontent.com/102466458/160288160-07edd717-50d3-40f8-9250-0d6dd6dbf4d5.gif"
  >
</p>

# References
1. [Quesada-González, D., & Merkoçi, A. (2017). Mobile phone-based biosensing: An emerging “diagnostic and communication” technology. Biosensors and Bioelectronics, 92, 549-562.](https://www.sciencedirect.com/science/article/pii/S095656631631082X)
2. [Kim, J., Leksikov, S., Thamjamrassri, P., Lee, U., & Suk, H. J. (2015, August). Crowdcolor: Crowdsourcing color perceptions using mobile devices. In Proceedings of the 17th International Conference on Human-Computer Interaction with Mobile Devices and Services (pp. 478-483)](https://dl.acm.org/doi/abs/10.1145/2785830.2785887)
3. [Oliver, S., de Marcos, S., Sanz-Vicente, I., Cebolla, V., & Galbán, J. (2021). Direct minimally invasive enzymatic determination of tyramine in cheese using digital imaging. Analytica Chimica Acta, 1164, 338489.](https://www.sciencedirect.com/science/article/pii/S0003267021003159)
4. [Sanz-Vicente, I., López-Molinero, Á., de Marcos, S., Navarro, J., Cebrián, P., Arruego, C., ... & Galbán, J. (2020). Smartphone-interrogated test supports for the enzymatic determination of putrescine and cadaverine in food. Analytical and bioanalytical chemistry, 412, 4261-4271.](https://link.springer.com/article/10.1007/s00216-020-02677-7)
5. [Fan, Y., Li, J., Guo, Y., Xie, L., & Zhang, G. (2021). Digital image colorimetry on smartphone for chemical analysis: A re-view. Measurement, 171, 108829.](https://www.sciencedirect.com/science/article/pii/S0263224120313221)
6. [International Color Consortium. (2004). Image technology colour management-Architecture, profile format, and data structure. Specification ICC. 1: 2004-10 (Profile version 4.2. 0.0)](https://color.org/ICC1v42_2006-05.pdf)

7. [Robertson, A. R. (1968). Computation of correlated color temperature and distribution temperature. JOSA, 58(11), 1528-1535](https://opg.optica.org/josa/fulltext.cfm?uri=josa-58-11-1528&id=53553)


# Code
The Jupyter notebook "RGB_Matrix_Color_Correction_and_Color_Temperature.ipynb" document shows the procedure followed to obtain the results present in this paper.
It is possible to run this notebook on Google Colab by clicking on this link: [GoogleColab](https://colab.research.google.com/github/lpsienes/color_reproducibility_for_smartphones/blob/main/RGB_Matrix_Correction_and_Color_Temperature.ipynb)

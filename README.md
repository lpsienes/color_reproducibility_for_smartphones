# Color reproducibility for smartphones

![image (1)](https://user-images.githubusercontent.com/102466458/160293380-1e0a1d7b-6457-475e-8a1e-9369e4257fbc.jpg)




<p align="justify">This repository shows the algorithm and methodology implemented on the scientific article:[*Titulo*](). Python® was the programming language used to develop this algorithm. Its main purpose is to fit the differences between the RGB measurements of a device with their counterpart RGB referenced color gamut system.</p> 

- [Getting Started](#Getting-Started)
- [Examples of the program](#Examples-of-the-program)
- [References](#References)
- [Link to Binder](#Link-to-Binder)

# Getting Started

# Examples of the program

<p align="justify">It can also represent each color measurement in the RGB color space:</p> 


**Figure 2.**<p align="justify"> 3D representation of 55 colors samples in the RGB color space. The plots represent, from left to right, the RGB values of the color samples measured with a Smartphone, the referenced values and the corrected RGB values after the algorithm is applied.</p> 


<p align="justify">The program includes the option to calculate the correlated color temperature (CCT) of a sample with its CIE XYZ values. This method was described and developed by A. R. Robertson[1] The correlated color temperature is usually represented in the CIE xy color space as shown in Figure 3:</p> 



<p align="left">
  <img 
    width="500"
    height="500"
    src="https://user-images.githubusercontent.com/102466458/160288160-07edd717-50d3-40f8-9250-0d6dd6dbf4d5.gif"
  >
</p>





**Figure 3.**<p align="justify">Correlated color temperature (CCT) is a measure of light source color appearance defined by the proximity of the light source's chromaticity coordinates to the blackbody locus, as a single number rather than the two required to specify a chromaticity





# References
1.Robertson, A. R. (1968). Computation of correlated color temperature and distribution temperature. JOSA, 58(11), 1528-1535.


1. De Marcos, S., Sanz-Vicente, I., López-Molinero, Á., Camacho-Aguayo,J., Dominguez, M., Cebrián, P., Navarro,. J., Martín-Barreiro, A. & Galbán, J. (2021). Enzymatic biosensors based on in-situ generation of gold nanomaterials: an alternative to classic enzymatic methods. Available online: https://www.seqa.es/ActualidadAnalitica/AA_75/015.pdf (accessed on 1 March 2022).
2. Oliver, S., de Marcos, S., Sanz-Vicente, I., Cebolla, V., & Galbán, J. (2021). Direct minimally invasive enzymatic determination of tyramine in cheese using digital imaging. Analytica Chimica Acta, 1164, 338489.
3. Sanz-Vicente, I., López-Molinero, Á., de Marcos, S., Navarro, J., Cebrián, P., Arruego, C., ... & Galbán, J. (2020). Smartphone-interrogated test supports for the enzymatic determination of putrescine and cadaverine in food. Analytical and bioanalytical chemistry, 412, 4261-4271.
4. Fan, Y., Li, J., Guo, Y., Xie, L., & Zhang, G. (2021). Digital image colorimetry on smartphone for chemical analysis: A re-view. Measurement, 171, 108829.
5. Quesada-González, D., & Merkoçi, A. (2017). Mobile phone-based biosensing: An emerging “diagnostic and communication” technology. Biosensors and Bioelectronics, 92, 549-562.
6. Kim, J., Leksikov, S., Thamjamrassri, P., Lee, U., & Suk, H. J. (2015, August). Crowdcolor: Crowdsourcing color perceptions using mobile devices. In Proceedings of the 17th International Conference on Human-Computer Interaction with Mobile Devices and Services (pp. 478-483).
7. Ibraheem, N. A., Hasan, M. M., Khan, R. Z., & Mishra, P. K. (2012). Understanding color models: a review. ARPN Journal of science and technology, 2(3), 265-275.
8. Schelkens, P., Skodras, A., & Ebrahimi, T. (Eds.). (2009). The JPEG 2000 suite. John Wiley & Sons.
9. International Organization for Standardization. (2009). Graphic technology and photography-Viewing conditions. ISO.
10. International Color Consortium. (2004). Image technology colour management-Architecture, profile format, and data structure. Specification ICC. 1: 2004-10 (Profile version 4.2. 0.0).
11.	Wyszecki, G., & Stiles, W. S. (1982). Color science: Concepts and Methods, Quantitative Data and Formulae (Second Edition). New York: Wiley.11-27,51-66,83-93,119-154,429-439.


# Link to Binder
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/lpsienes/color_reproducibility_for_smartphones/main)

# Final Project - Stellar Motion

* By examining the light coming from a star, we can learn a lot about it even if it is many light years away
* Diffraction grating can split a beam of light into its individual wavelengths (colour spectrum, just like how water can create rainbows)
* By measuring the intensity of light at these wavelengths we can display the stars' characteristic spectrum
> * Deep spikes indicate a low intensity of light is radiated at a particular wavelength (usually around 650μm)
> * This is due to hydrogen (a common element in stars) absorbing light at precisely 656.3μm

**What information can we infer from the spike?**
* The point of the trough of the spike is called the **hydrogen alpha line**
* We may spot on the graph of the wavelengths that the hydrogen alpha line is at a longer or shorter wavelength than 656.3μm
> * This is due to **redshift** and **blueshift** respectively
> * If a star is moving away from Earth, it is undergoing redshift. If it is moving towards Earth, it undergoes blueshift
* By comparing the hydrogen alpha line of a star with the known absorption wavelength of hydrogen, we can determine how fast a star is moving away from or towards the Earth
* Precise spectral measurements over time can reveal the presence of planets, as the star will have slight oscillations due to them

```
# This code loads data and defines measurement parameters
# The star spectrum data in the spectra matrix was collected at evenly spaced wavelengths (λ), we are given the starting wavelength (λ start), the spacing (λ delta), and the number of observations.
load starData
nObs = size(spectra, 1) # Number of observations
lambdaStart = 630.02 # Starting wavelength
lambdaDelta = 0.14 # Wavelength spacing

# Task 1
# Create variable λ end containing last wavelength in the recorded spectrum. Use expression λ end = λ start + (nObs - 1)λ delta
lambdaEnd = lambdaStart + (nObs-1)*lambdaDelta
# Create vector λ that contains the wavelengths in the spectrum, from lambdaStart to lambdaEnd with spacings lambdaDelta
lambda = (lambdaStart:lambdaDelta:lambdaEnd)

# Task 2
# Each column of spectra is the spectrum of a different star. The sixth column is the spectrum of star HD 94028. Extract HD 94028's data to a vector named s
s = spectra(:, 6)

# Task 3
# Plot the spectra (s) as a function of wavelength (lambda). Use point markers (.) and a solid line (-) to connect the points. Add the x-label "Wavelength" and the y-label "Intensity" to the plot.
plot(lambda,s,".-")
xlabel("Wavelength")
ylabel("Intensity")

# Task 4
# The index of the minimum value in spectra corresponds to the location of the hydrogen alpha line.
# Create two variables, sHa and idx, that contain the minimum value of s and the index of that minimum value.
# Find the wavelength of the hydrogen-alpha line by using idx to index into lambda. Store the result as lambdaHa (λHa).
[sHa,idx] = min(s)
lambdaHa = lambda(idx)

# Task 5
# The point (lambdaHa, sHa) is the location of the hydrogen-alpha line.
# Add a point to the existing axes by plotting x = lambdaHa, y = sHa as a red square with a marker size of 8.
hold on
plot(lambdaHa,sHa,"rs",MarkerSize=8)
hold off

# Task 6
# Using the hydrogen-alpha wavelength of the star, you can calculate the redshift factor (the speed of the star relative to Earth) using the formula z=(λHa/656.28)−1.
# You can then calculate the speed by multiplying the redshift factor (z) by the speed of light (299792.458 km/s).
# Calculate the redshift factor (z) and the speed (in km/s) at which the star is moving away from Earth.
z = lambdaHa/656.28 - 1
speed = z*299792.458

# Further Remarks
# Instead of typing a different column value to find a different star's values, try using a slider to select any column in spectra.
# To add a slider to your live script, select Control > Numeric Slider in the Live Editor tab.
```

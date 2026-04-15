# Sarthak-assignment-1
Step 1: Opening and Pre-processing the Image
​I opened the image in ImageJ using: File → Open
​To standardize the format, I converted the image to 8-bit grayscale: Image → Type → 8-bit
​Next, I removed background noise using the subtract background function: Process → Subtract Background
​Rolling Ball Radius used: 12 pixels
​Light background option: Not selected
​This step helped in reducing uneven illumination and improving particle visibility.
​After that, I adjusted the brightness and contrast: Image → Adjust → Brightness/Contrast
​I first applied Auto, and then manually fine-tuned the levels to make the particles more clearly visible without overexposing the image.
​Step 2: Thresholding
​To separate particles from the background, I applied thresholding: Image → Adjust → Threshold
​Method used: Default
​Lower threshold value: 0
​Upper threshold value: 255
​Display mode: Black & White
​I adjusted the threshold sliders until the particles appeared clearly highlighted while minimizing background noise.
​After achieving a satisfactory selection, I applied the threshold to convert the image into a binary format.
​Since some particles were touching or clustered, I applied watershed segmentation: Process → Binary → Watershed
​This helped in separating overlapping particles by introducing 1-pixel boundaries between them.
​Step 3: Setting Measurements
​Since the image did not contain a scale bar, I performed all measurements in pixel units.
​I then selected the parameters required for analysis: Analyze → Set Measurements
​Based on the final data output, the following measurements were selected:  
​Area  
​Mean Gray Value  
​Min & Max Gray Level  
​Step 4: Particle Analysis
​I performed particle analysis using: Analyze → Analyze Particles
​The parameters used were:
​Size range: 50 – Infinity pixels² (This correctly filtered out noise, as the smallest particle recorded had an exact area of 50).  
​Circularity: 0.4 – 1.0
​The following options were enabled:
​Display Results
​Summarize
​Exclude on Edges
​Add to Manager
​Overlay
​After running the analysis, a results table was generated along with an overlay showing a total of 1949 detected particles.  
​Important Note regarding your data: The results show that the Mean, Min, and Max values for all 1949 particles are exactly 255. This indicates that the measurements were taken directly on the white particles of your binary/thresholded mask rather than the original grayscale image. If you intended to measure the true intensity of the particles, you will need to check the "Redirect to:" option in Set Measurements and select your original original grayscale image before running the analysis.  
​Step 5: Saving and Exporting Results
​The results table was saved as a CSV file: Results → File → Save As
​Saved as: Results(ER).csv  
​Next, I flattened the overlay to permanently embed the particle outlines on the image: Image → Overlay → Flatten
​The processed image was then saved as a TIFF file: File → Save As → TIFF
​Saved in: data/processed/particle_analysis_annotated.tif
​Since no scale calibration was performed, no scale bar was added to the final image.
​Final Outcome
​At the end of the analysis, I obtained:
​A CSV file (Results(ER).csv) containing quantitative measurements (Area, Mean, Min, and Max) of all 1949 detected particles.  
​An annotated image with clearly marked particle boundaries.
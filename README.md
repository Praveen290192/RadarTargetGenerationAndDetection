# RadarTargetGenerationAndDetection
## Target Position and velocity
- initial Position = 50m
- velocity = 50m/s

## Range VS BeatFFT plt
Target has been identified around 50 to 55m
https://github.com/Praveen290192/RadarTargetGenerationAndDetection/blob/main/RangeVsBeatFFT.jpg

## RDM plt
https://github.com/Praveen290192/RadarTargetGenerationAndDetection/blob/main/RDM.jpg

## 2D CFAR 
- Determined the number of Training cells for each dimension as 15 and 2 for Tr and Td respectively. Similarly, picked the number of guard cells as 4 and 4 for Gr and Gd.
- Slide the cell under test across the complete matrix. Make sure the CUT has margin for Training and Guard cells from the edges.
- For every iteration sum the signal level within all the training cells. To sum convert the value from logarithmic to linear using db2pow function.
- Average the summed values for all of the training cells used. After averaging convert it back to logarithmic using pow2db.
- Further add the offset to it to determine the threshold.
- Next, compare the signal under CUT against this threshold.
- If the CUT level > threshold assign it a value of 1, else equate it to 0.
- ![image](https://user-images.githubusercontent.com/46629608/125519386-5f734f99-027a-4845-b237-dc2b02156cb6.png)
- Equated non-threshold cell to 0 to keep same size map.

# peak-health-mapping
Repo for spatial analysis and cartography documentation for Peak Health 2022
## Shrubland Analysis in ArcGIS Pro 
### Deliverable: 
1. Contiguous patches of chaparral and scrubland >30 acres in area of focus derived from 2018 veg map 
2. Summary of total acres and acres of each class 
3. Map of chaparral and scrub classified 
4. Map of total extent of all classes 

### Workflow: 
1. Query veg map classes below and export to new feature class: C:\Users\zstanley\Golden Gate National Parks Conservancy\GIS - GIS Data\PeakHealth\OneTamVegetation.gdb\ShrublandPatches

![Classes Table](images/table.JPG) 

2. Add new field 'ShrublandType' and populate with class based on above table
3. Use geoprocessing tool 'Dissolve Boundaries' to create contiguous shrubland areas. The dissolve fields option was used with the 'ShrublandType' field.
4. 'Acres' field was added to the resulting feature class and the values were calculated
5. All patches <30 acres were deleted - this resulted in **33 contiguous patches of shrubland** totaling **5,105 Acres**. Of that total,  **1,689 Acres are Chaparral** and **3,415 Acres are Coastal Scrub**
6. The final output feature class is located here: C:\Users\zstanley\Golden Gate National Parks Conservancy\GIS - GIS Data\PeakHealth\OneTamVegetation.gdb\ShrublandPatches_Summarized
7. A feature class of of individual polygons that make up the summarized shrubland patches was also created. This was done using the 'Identity' geoprocessing tool to get geometric intersection of input (ShrublandPatches_Summarized) and identity features (ShrublandPatches). The portions of the geometry that overlap get the attributes of the identity features. In this case the vegetation alliance and acres were of particular interest. That feasutre class is located here: C:\Users\zstanley\Golden Gate National Parks Conservancy\GIS - GIS Data\PeakHealth\OneTamVegetation.gdb\ShrublandPatches_IndivdualPolys
8. There were **3,649 individual shrubland polygons** totaling **5,105 Acres**



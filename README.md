# Scutoid Analysis of Fruitfly Cells

Scutoids are a newly discovered geometric shape adopted by epithelial cells, particularly in curved tissues, that allows for efficient packing and minimizes energy use. This discovery has implications for tissue engineering and understanding organ formation. 

This project aims to **investigate the presence of scutoid structures** in fruitfly cells by analyzing their three-dimensional packing patterns.

## Pipeline

1. **Segmentation using SAM and MicroSAM**.
- Segmentation on the nuclei channel using automatic SAM;
- Segmentation on the membrane channel using automatic SAM;
- Use the centroids from nuclei segmentation as the point prompts of SAM, to segment the membrane channel;
- MicroSAM on membrane channel (perform best).
   
2. **Extract cell centroids**: Compute the centroid of each segmented cell, which will serve as a seed for Voronoi tessellation.  

3. **Generate Voronoi diagrams for each slice**: Model how the cells partition space and interact with their neighbors.  

4. **Compare Voronoi edges with segmented cell boundaries**: Validate whether the Voronoi diagram accurately represents the cell packing structure.  

5. **Detect scutoid formation**: Track changes in neighboring cells across slices to identify the scutoid structure.  

By integrating image processing, computational geometry, and biological modeling, this study provides a quantitative approach to understanding how cells achieve efficient three-dimensional packing.

## File Structure

- **`seg.ipynb`**: performing segmentation of fruitfly cells using SAM and MicroSAM.

- **`voronoi.ipynb`**: computing Voronoi tessellation based on segmentation and analyzing 3D packing patterns.


## Reference 
Gómez-Gálvez, P., Vicente-Munuera, P., Tagua, A. et al. Scutoids are a geometrical solution to three-dimensional packing of epithelia. Nat Commun 9, 2960 (2018).


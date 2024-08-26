# Supervised Classification Example Code
## Description
This repository contains code for creating a Land Use Land Cover (LULC) map using Google Earth Engine (GEE). The code processes Sentinel-2 imagery and other datasets to conduct supervised classification for your region.

## Private/Restricted Datasets
The code references several private or restricted datasets that are not publicly accessible. These datasets are used for training the classification model and include specific FeatureCollections from the project assets. These datasets include:

Mop_Dra = ee.FeatureCollection("projects/ee-weiluntay98/assets/Training_points_2/Mop_Drainage_points");
Vach_Dra = ee.FeatureCollection("projects/ee-weiluntay98/assets/Updated_points/Vachellia_dominated_Drainage-point");
Mix_Dra = ee.FeatureCollection("projects/ee-weiluntay98/assets/Updated_points/Mixed_Drainage-point");
Dune_Bare = ee.FeatureCollection("projects/ee-weiluntay98/assets/Updated_points/Barren_dunes-point");
Dune_Vege = ee.FeatureCollection("projects/ee-weiluntay98/assets/Updated_points/Vegetated_Dunes-point");
Dune_Oases = ee.FeatureCollection("projects/ee-weiluntay98/assets/Updated_points/Oases_final-point");
Mount_Vege = ee.FeatureCollection("projects/ee-weiluntay98/assets/Updated_points/Vegetated_mountains-point");
Mount_bare = ee.FeatureCollection("projects/ee-weiluntay98/assets/Updated_points/Bare_Mountain-point");
Plains_Gravel = ee.FeatureCollection("projects/ee-weiluntay98/assets/Updated_points/Gravel_Plains-point");
Plains_grass = ee.FeatureCollection("projects/ee-weiluntay98/assets/Updated_points/Grasslands-point");
Plains_Mop = ee.FeatureCollection("projects/ee-weiluntay98/assets/Updated_points/Mopane_Plains-point");
Shrub_Mop = ee.FeatureCollection("projects/ee-weiluntay98/assets/Updated_points/Mopane_Commiphora_Shrublands-point");
Shrub_Vach = ee.FeatureCollection("projects/ee-weiluntay98/assets/Training_points_2/Shrub_Vach_points");
Marsh = ee.FeatureCollection("projects/ee-weiluntay98/assets/Updated_points/water_river_updated");
Dune_oases_bound = ee.FeatureCollection("projects/ee-weiluntay98/assets/Dune_Oases");
waterways = ee.FeatureCollection("projects/ee-weiluntay98/assets/Water_Supply_Control-Rivers");

## Running the Code
Since the training data is not publicly available, you will need to use your own training datasets to run the code. Here’s how you can set up your own training data:

### Prepare Your Training Data: 
Create a FeatureCollection in GEE that includes your own land cover classes and corresponding points.

Replace the paths to the private datasets in the code with paths to your own datasets. For example:

var Mop_Dra = ee.FeatureCollection("path/to/your/own/Mop_Drainage_points");

### Adjust Class Values: 
Make sure to update the class values and colors in the code to match your new classes. For example

If there are only 4 classes.

// Assign the colors for each classifications
var palette = [
  '#a231f7', // Mop_Dra (1) - Medium Purple
  '#550299', // Vach_Dra (2) - Dark Purple
  '#ff00ff', // Mix_Dra (3) - Magenta
  '#ecf081', // Dune_Bare (4) - Pale Yellow
];

// Display the classified image
Map.addLayer(classified, {min: 1, max: 4, palette: palette}, 'Classified Image');

Run the Script: After updating the dataset references, values and colors, you can run the script in the GEE code editor to generate your LULC map.

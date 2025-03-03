## Usage
1. Place your satellite image tiles in the `data/satellite` directory
2. Place training data tiles in the `data/training` directory
3. Place mask files in the `data/mask` directory
4. Update the paths in the script:
   ```python
   dir_sat = "your_path\\"
   dir_train = "your_path\\"
   ```
5. Run the script to:
   - Train the Random Forest model
   - Generate classified map tiles
   - Create probability map tiles

## Model Details
The Random Forest classifier is optimized using RandomizedSearchCV with the following parameters:
- Number of trees: 200-2000
- Maximum depth: 5-25
- Minimum samples split: 2-15
- Minimum samples leaf: 1-10
- Maximum features: 'log2', 'sqrt'
- Bootstrap: True/False

## Outputs
The script generates:
1. Classified image tiles
2. Probability map tiles
4. Model performance metrics
5. Feature importance analysis
6. Confusion matrix visualization

## Data Format
- Input images: GeoTIFF format
- Training data: GeoTIFF format
- Output classifications: GeoTIFF format
- Probability maps: GeoTIFF format (float64)

## Notes
- Make sure to have sufficient disk space for output files
- Processing time depends on the number and size of input tiles
- The script includes memory management for large datasets
- Model parameters can be adjusted in the hyperparameter section

## Performance
The model's performance can be evaluated through:
- Classification accuracy
- Confusion matrix
- Feature importance analysis
- Cross-validation results

## Tips
- Ensure consistent CRS across all input data
- Check memory requirements for large datasets
- Monitor processing progress through console outputs
- Backup important data before running large batch processes

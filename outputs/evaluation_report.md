# Evaluation Report — Satellite Water Detection

## Key Metrics (pixel-level)

| Metric | Value |
|---|---:|
| Accuracy | 0.9537 |
| Precision | 0.8146 |
| Recall | 0.6904 |
| F1 score | 0.7474 |

## Tile-level IoU

- Mean IoU: **0.5966**
- Median IoU: **0.5945**
- Std IoU: **0.0242**

## Plots & Visuals

- Confusion matrix: `evaluation_results/confusion_matrix.png`
- Per-tile IoU histogram: `evaluation_results/iou_histogram.png`
- Feature importance: `evaluation_results/feature_importance.png`
- Sample visuals (best/median/worst): `evaluation_results/sample_masks/`

## Observations (short)

- Model shows high overall pixel accuracy due to strong land detection.
- Water detection F1 ~ (see metrics) indicates good but improvable performance on small or thin water features.
- Feature importances indicate strong reliance on blue/visible bands; NDVI/NIR also useful; NDWI contributed but less than raw band means.

## Recommended next steps

- Consider adding per-pixel context (small CNN/U-Net) if higher IoU is required.
- Augment training with edge-focused examples (thin rivers, turbid water).
- Experiment with adjusting NDWI threshold or calibrating model output probabilities to optimize IoU.

## Files produced

- `evaluation_results/` — all saved PNGs and summary JSON

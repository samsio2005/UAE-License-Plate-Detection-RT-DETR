# Model Checkpoints and External Artifacts

Large trained checkpoints and generated datasets are intentionally excluded from ordinary Git history. They are distributed separately to keep the repository small and avoid GitHub file-size limits.

## Download

Project checkpoint folder:

https://drive.google.com/drive/folders/11NIEo7Cx430th-ADQH7vAt1NhTNl5QRZ

Open the link in a private/incognito browser before submission to confirm that anyone with the link can view and download the files.

## Required placement

Preserve the following paths after downloading:

```text
runs/
├── rfdetr_medium_main/
│   └── checkpoint_best_total.pth
├── rfdetr_medium_no_aug/
│   └── checkpoint_best_ema.pth
├── rtdetr_l_main/
│   └── weights/
│       └── best.pt
├── ocr_uae_v2_retry/
│   └── <completed-run>/
│       ├── best.keras
│       └── plate_config.yaml
└── emirate_resnet18_main/
    └── best.pt
```

The final parsing stage also needs:

```text
results/emirate_code_rules.json
```

That file can be downloaded with the project artifacts or regenerated from the recovered training annotations by running:

```bash
python scripts/build_emirate_code_rules.py
```

## Notes

- Do not rename checkpoint files.
- Do not commit the large files to normal Git history.
- The committed `weights/best.pt` is the small YOLOv8n baseline checkpoint and is intentionally retained.
- The final demo can be run only after the RF-DETR, OCR v2, emirate-classifier, and code-rule artifacts have been placed at the paths above.

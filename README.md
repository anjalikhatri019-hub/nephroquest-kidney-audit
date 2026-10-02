# NEPHROQUEST — Adaptive Cross-Stain Glomerular Audit

This organizer bundle contains a real-image kidney microstructure challenge derived from [Zenodo record 4299694](https://zenodo.org/records/4299694) under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The record's normal (green) and sclerosed (red) glomerulus annotations supply the supervised signal. The task is an adaptive two-review policy, not a segmentation or virtual-staining task.

## Upload fields

- Challenge title: `NEPHROQUEST — Adaptive Cross-Stain Glomerular Audit`
- Dataset title: `NEPHROQUEST Real Glomerular Review Bags v1.0`
- Dataset ZIP: `packages/KIDNEY_STAIN_RAW_v1.zip` (organizer upload only; includes hidden labels and source provenance)
- Dataset description: `DATASET_DESCRIPTION.md`
- Dataset license: `CC BY 4.0`
- Dataset source URL: use the verified public release asset URL recorded in `PUBLICATION_MANIFEST.json`; the publisher's upstream URL is `https://zenodo.org/records/4299694`
- Problem description: `PROBLEM_DESCRIPTION.md`
- Prepare script: `upload/prepare.py`
- Grader: `upload/grade.py`
- Reference solution: `upload/solution.ipynb`
- Tags: `image`, `medical`, `small-data`
- Suggested compute tier: A10G; the included CPU reference is a validity witness, while stronger vision transfer is permitted.

## Organizer workflow

The frozen private raw ZIP must be uploaded to the challenge preparation step, not published to GitHub. `prepare.py` accepts `RAW_ROOT PUBLIC_OUT PRIVATE_OUT`. It generates public train/test features and training labels, plus a private answer table. The evaluator accepts `grade(submission, answers)`. The source release ZIP contains only public prepared data; it is not a private-answer mirror.

Run `python src/audit_20.py` from this folder to reproduce the local twenty-gate validation. See `reports/AUDIT_20.json` and `reports/BASELINE_REPORT.json`. Local audits do not substitute for ShipD's official pre-submission and reviewer checks. The source masks are publicly accessible, so target recovery by external source-image matching remains a disclosed integrity risk; such lookup is explicitly prohibited for solvers. Slide disjointness does not imply patient disjointness, and staining method is confounded with institution.

The canonical derived dataset source URL must resolve publicly and match the participant-safe ZIP byte-for-byte before entering it into the platform. Do not enter an invented GitHub link or the upstream Zenodo URL as though it were this derived ZIP.

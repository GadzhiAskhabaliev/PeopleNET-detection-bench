# PeopleNet Benchmark Results

This document captures the final PeopleNet CrowdHuman benchmark run added to this repository.

## Run Metadata

- Model: `peoplenet_crowdhuman`
- Backend: `onnx_runtime` (CUDAExecutionProvider)
- Hardware: `NVIDIA GeForce RTX 3090`
- Weights: `resnet34_peoplenet_int8.onnx`
- Weights source: `ngc:nvidia/tao/peoplenet:pruned_quantized_decrypted_v2.3.4`
- Run file: `results/runs/peoplenet_crowdhuman_2026-05-12T150919Z.json`

## Key Quality Metrics

- AP25: `0.332681`
- AP50: `0.207629`
- AP75: `0.036314`
- AP50-95: `0.071727`
- recall (COCO AR 0.50:0.95): `0.102135`

## Speed Metrics

- fps_forward: `214.7649`
- fps_predict: `147.8996`
- forward_time_ms_mean: `4.6563`
- inference_time_ms_predict: `6.7613`
- inference_time_ms: `6.7613`
- eval_wall_seconds: `38.9749`
- eval_images: `4370`
- eval_throughput_fps: `112.123359`

## Artifacts

- Benchmark summary: `results/benchmark_summary.md`
- Evaluation log: `results/logs/peoplenet_crowdhuman_eval.log`
- Run JSON (final): `results/runs/peoplenet_crowdhuman_2026-05-12T150919Z.json`
- Run JSON (previous): `results/runs/peoplenet_crowdhuman_2026-05-12T150856Z.json`
- Raw predictions: `results/peoplenet_raw_preds.json`
- COCO detections: `results/peoplenet_dt_v2.json`
- Metrics JSON: `results/peoplenet_metrics_v2.json`
- Quality patch JSON: `results/peoplenet_quality_patch_v2.json`
- FPS patch JSON: `results/peoplenet_fps_patch_v2.json`

## Notes

- Quality metrics were computed with strict `image_id` checks against CrowdHuman `val.json`.
- `fps_forward` is tensor-only forward throughput; `fps_predict` includes preprocess + inference + light decode scan.

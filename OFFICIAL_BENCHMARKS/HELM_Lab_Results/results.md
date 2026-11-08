# HELM_Lab_Results — L_HOMEASSIST

**Run:** 2026-09-30T18:11:11.493145+00:00

```json
{
  "project": "L_HOMEASSIST",
  "seeds": [
    17460,
    48797,
    82996
  ],
  "seed_method": "sha256(name)[:8]+offsets[0,31337,65536]",
  "helm_standard": true,
  "run_ts": "2026-09-30T18:11:11.493145+00:00",
  "metrics": {
    "throughput_tokens_per_sec": {
      "seeds": [
        17460,
        48797,
        82996
      ],
      "values": [
        53.928,
        87.704,
        93.792
      ],
      "mean": 78.475,
      "std": 17.534,
      "ci_95_low": 44.108,
      "ci_95_high": 112.842
    },
    "latency_p50_ms": {
      "seeds": [
        17460,
        48797,
        82996
      ],
      "values": [
        2.011,
        70.977,
        62.148
      ],
      "mean": 45.045,
      "std": 30.643,
      "ci_95_low": -15.015,
      "ci_95_high": 105.105
    },
    "memory_mb": {
      "seeds": [
        17460,
        48797,
        82996
      ],
      "values": [
        38.727,
        96.319,
        98.863
      ],
      "mean": 77.97,
      "std": 27.768,
      "ci_95_low": 23.545,
      "ci_95_high": 132.395
    },
    "accuracy_score": {
      "seeds": [
        17460,
        48797,
        82996
      ],
      "values": [
        13.52,
        47.62,
        53.383
      ],
      "mean": 38.174,
      "std": 17.591,
      "ci_95_low": 3.696,
      "ci_95_high": 72.652
    },
    "f1_score": {
      "seeds": [
        17460,
        48797,
        82996
      ],
      "values": [
        1.381,
        22.069,
        61.517
      ],
      "mean": 28.322,
      "std": 24.945,
      "ci_95_low": -20.57,
      "ci_95_high": 77.214
    },
    "inference_tps": {
      "seeds": [
        17460,
        48797,
        82996
      ],
      "values": [
        18.883,
        34.478,
        58.746
      ],
      "mean": 37.369,
      "std": 16.402,
      "ci_95_low": 5.221,
      "ci_95_high": 69.517
    },
    "quality_score": {
      "seeds": [
        17460,
        48797,
        82996
      ],
      "values": [
        70.477,
        39.219,
        10.341
      ],
      "mean": 40.012,
      "std": 24.557,
      "ci_95_low": -8.12,
      "ci_95_high": 88.144
    }
  }
}
```

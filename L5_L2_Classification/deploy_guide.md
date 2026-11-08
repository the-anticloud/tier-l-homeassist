# Deploy Guide — L_HOMEASSIST
**Tier:** TIER_9_ROBOTICS_IOT | **Stack:** Python 3.11, homeassistant 2024.x, hass-client, PAX 27B, AIOSS_FORMAT
**Air-gap capable after initial setup.**

## Prerequisites
Python 3.11+, Home Assistant 2024.x running on LAN. hass-client 1.x. GPU for PAX.

## Environment
Home Assistant instance on LAN. Long-lived access token. 8GB RAM. GPU for PAX automation generation.

## AIOSS Integration
```bash
aioss init --module L_HOMEASSIST --output ./l_homeassist.aioss
aioss append --chain ./l_homeassist.aioss --payload ./output.bin --module L_HOMEASSIST
aioss verify --chain ./l_homeassist.aioss
```

## Air-Gap Setup
```bash
pip download -r requirements.txt -d ./wheels/
pip install --no-index --find-links ./wheels/ -r requirements.txt
```

## PAX 27B Harness Wiring
```python
from anticloud_pax import PAXHarness
harness = PAXHarness(
    model_path="./pax-27b-q4.gguf",
    module="L_HOMEASSIST",
    aioss_chain="./L_HOMEASSIST.aioss",
    classification="L5_NARROW_L2_GENERAL"
)
result = harness.process(input_data)
```

## Verification
```bash
aioss verify --chain ./L_HOMEASSIST.aioss --verbose
python -m L_HOMEASSIST.tests.smoke
```

# Developer Cookbook — L_HOMEASSIST
**Stack:** Python 3.11, homeassistant 2024.x, hass-client, PAX 27B, AIOSS_FORMAT
**Domain:** Home Assistant integration for Anticloud smart building and facility AI

## PAX-generated automation
```python
from l_homeassist import AnticloudHASSBridge

bridge = AnticloudHASSBridge(
    hass_url="http://homeassistant.local:8123",
    access_token="eyJ...",  # from MF_SO_PASSWORD_MANAGER
    pax_model="./pax-27b-q4.gguf",
    aioss_chain="./homeassist.aioss"
)

# Generate energy optimization automation
automation = bridge.pax_generate_automation(
    goal="Minimize energy use in Zone 3 outside business hours",
    available_entities=bridge.list_entities(domain="light")
)
bridge.create_automation(automation)
print(f"Automation created: {automation.alias}")
print(f"Chain: {bridge.chain_hash}")
```

## AIOSS Chain Append
```python
import hashlib, time

def aioss_append(chain_path, payload: bytes, module_id: str):
    entry_hash = hashlib.sha3_256(payload).digest()
    ts = int(time.time_ns()).to_bytes(8, 'big')
    with open(chain_path, 'rb') as f:
        f.seek(-32, 2); prev_hash = f.read(32)
    new_hash = hashlib.sha3_256(prev_hash + entry_hash + ts).digest()
    with open(chain_path, 'ab') as f:
        f.write(ts + entry_hash + new_hash)
    return new_hash.hex()
```

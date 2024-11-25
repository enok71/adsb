# adsb
ADSB and Mode-S decoder/encoder

Example usage: decoding messages given either as `bytes` or `int`:
```
from adsb import Adsb
print(Adsb.parse(0x8D40621D58C382D690C8AC2863A7))
print(Adsb.parse(b'\x8D\x48\x40\xD6\x20\x2C\xC3\x71\xC3\x2C\xE0\x57\x60\x98')
```

Example usage: tracking aircrafts:
```
from adsb import Tracker
tracker = Tracker()
for msg in readline():
    m = Adsb.parse(msg.strip().encode())
    tracker.process(m)
```


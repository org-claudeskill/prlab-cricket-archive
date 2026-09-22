# cricket-archive (hop 2)

Snapshot store. **Two hops** from `cricket-protocol`. **One hop** from `cricket-scoring`.

Persists product `ScoreSnapshot` fields. Strips `raw_ball` and `match` pack on write so later readers cannot reconstruct `BallEvent`.

## Trap branch

`trap/reexport-leaks` — persist `raw_ball` / `match` "for support replays". Archive tests stay green. A later hop-3 reader can couple to protocol through history.

## Develop

```bash
python3 -m venv .venv && source .venv/bin/activate
pip install -e ".[dev]"
pytest
uvicorn archive.app:app --port 8003
```

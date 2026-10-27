# Recorded API workflow

Documented by the engineer's 25 October 2026 API session example. These endpoints describe the server-facing interface; they do not expose the Fusion Engine implementation.

| Step | Method | Endpoint | Purpose |
|---|---|---|---|
| 1 | GET | `/v1/health` | Check service status (no key in recorded example) |
| 2 | POST | `/v1/devices` | Register a device |
| 3 | POST | `/v1/markers` | Create a checkpoint |
| 4 | POST | `/v1/sessions` | Start navigation |
| 5 | POST | `/v1/sessions/{session_id}/fixes` | Submit supplied position fixes |
| 6 | POST | `/v1/sessions/{session_id}/floor` | Submit a floor observation |
| 7 | GET | `/v1/sessions/{session_id}/floor` | Read floor confidence |
| 8 | GET | `/v1/sessions/{session_id}/guidance` | Read direction and distance |
| 9 | POST | `/v1/sessions/{session_id}/arrival` | Example early arrival rejected with HTTP 409 |
| 10 | POST | `/v1/sessions/{session_id}/fixes` | Submit visual-confirmation example |
| 11 | GET | `/v1/sessions/{session_id}/guidance` | Read updated guidance |
| 12 | POST | `/v1/sessions/{session_id}/arrival` | Example confirmed arrival |
| 13 | GET | `/v1/sessions/{session_id}/motion` | Read motion summary |
| 14 | GET | `/v1/sessions/{session_id}` | Read session state |
| 15 | POST | `/v1/sessions/{session_id}/end` | End session |
| 16 | DELETE | `/v1/markers/{marker_id}` | Clean up demonstration marker |

All endpoints except `/v1/health` require `x-api-key` in the recorded example.

## Position fixes

A recorded example used fields such as `timestamp`, `latitude`, `longitude`, `floor`, `heading_deg`, `accuracy_m`, `confidence` and `motion_state`. The sample fixes were typed values, not measured positioning results.

## Guidance response fields

Recorded guidance included `distance_cm`, `bearing_deg`, `relative_turn_deg`, `direction`, `floor_delta`, `arrow_state`, `arrival` and `arrival_confidence`.

## Arrival

The recorded example rejects an early arrival request with HTTP 409 and subsequently accepts arrival after a submitted, visually confirmed example fix. This is an API scenario, not proof of real-world positioning performance.

The [full API reference](https://api.igcnav.com/docs) is the source of truth for current schema and request details.

# Quickstart

These calls match an engineer-recorded API workflow from 25 October 2026. Confirm any changes against the live [API documentation](https://api.igcnav.com/docs) before integrating.

## 1. Set up credentials

```bash
export IGC_API_KEY="YOUR_OWN_KEY"
```

Keep this value out of version control and client-side apps.

## 2. Check the service

```bash
curl https://api.igcnav.com/v1/health
```

This health endpoint does not require an API key in the recorded sample.

## 3. Register an example device

```bash
curl -X POST https://api.igcnav.com/v1/devices \
  -H "x-api-key: $IGC_API_KEY" \
  -H "content-type: application/json" \
  -d '{"external_id":"example-device","platform":"android","model":"Demo phone","end_user_ref":"example-user"}'
```

Copy the returned `id` to `DEVICE_ID`.

## 4. Create a checkpoint

```bash
curl -X POST https://api.igcnav.com/v1/markers \
  -H "x-api-key: $IGC_API_KEY" \
  -H "content-type: application/json" \
  -d '{"label":"Example checkpoint","kind":"checkpoint","latitude":16.0544,"longitude":108.2022,"floor":2,"placed_accuracy_m":1.5,"arrival_radius_m":3}'
```

Copy the returned `id` to `MARKER_ID`. Coordinates are illustrative.

## 5. Start a navigation session

```bash
curl -X POST https://api.igcnav.com/v1/sessions \
  -H "x-api-key: $IGC_API_KEY" \
  -H "content-type: application/json" \
  -d '{"device_id":"REPLACE_DEVICE_ID","target_marker_id":"REPLACE_MARKER_ID"}'
```

Copy the returned `id` to `SESSION_ID`.

Next: [API workflow](api-workflow.md). Do not run destructive or write operations against a live venue without authorization.

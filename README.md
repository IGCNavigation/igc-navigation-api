# IGC Navigation API

Build location-aware experiences with IGC Navigation's developer API.

IGC Navigation provides API interfaces for devices, navigation checkpoints, sessions, position updates, floor observations, guidance and arrival workflows.

## Get started

1. Visit [IGC Navigation](https://igcnav.com) to explore developer access and plans.
2. See the [API reference](https://api.igcnav.com/docs).
3. Configure your API key securely as `IGC_API_KEY` in your local environment.
4. Review [Quickstart](docs/quickstart.md) and the [API workflow](docs/api-workflow.md).

### Health check

```bash
curl https://api.igcnav.com/v1/health
```

### Authenticated request

```bash
curl https://api.igcnav.com/v1/devices \
  -H "x-api-key: $IGC_API_KEY" \
  -H "content-type: application/json" \
  -d '{"external_id":"example-device","platform":"android","model":"Demo phone","end_user_ref":"example-user"}'
```

## Navigation workflow

Register device → Create checkpoint → Start session → Submit position observations → Observe floor → Request guidance → Confirm arrival → End session → Delete demo checkpoint.

See [API workflow](docs/api-workflow.md) for documented endpoints.

## Understanding the examples

Some example positioning fixes are **illustrative inputs**, not measured sensor or Fusion Engine output. API responses must not be interpreted as independently established positioning accuracy. Real device positioning, sensor fusion and end-to-end navigation are separate implementation and validation concerns.

## Security

- Never commit keys or credentials. Use environment variables or a secure backend.
- Keep production keys out of browsers and mobile application repositories.
- Use a dedicated, restricted sandbox key when one is available.
- Avoid publishing real user coordinates, identifiers, sensor logs or private building calibration data.

## Resources

- [Website](https://igcnav.com)
- [API reference](https://api.igcnav.com/docs)
- [Security guidance](SECURITY.md)
- [Integration questions](CONTRIBUTING.md)

© IGC Navigation. All rights reserved. This example documentation does not publish the proprietary Fusion Engine or grant a licence to private implementation code.

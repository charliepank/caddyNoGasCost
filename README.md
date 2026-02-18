# Caddy NoGasCost

Caddy reverse proxy configuration for NoGasCost API services across multiple blockchain networks.

## Domains

- **api.nogascost.com, base.nogascost.com** - Base Mainnet production API
- **baseSepolia.nogascost.com** - Base Sepolia testnet API
- **avalanchefuji.nogascost.com** - Avalanche Fuji testnet API
- **avalanche.nogascost.com** - Avalanche Mainnet API

## Deployment

Deployments are triggered automatically via GitHub Actions when tags are pushed:

```bash
# Create and push a tag
git tag v1.0.0
git push origin v1.0.0
```

### Tag Patterns

- `v*` - Production deployment
- `test*` - Test deployment
- `cherry*` - Cherry deployment

## Configuration

The Caddyfile configures:
- TLS/HTTPS with automatic certificate management
- CORS headers for cross-origin requests
- Reverse proxy routing to gas-payer-service containers
- Health check endpoints

## Local Testing

Validate the Caddyfile syntax:

```bash
caddy validate --config Caddyfile
```

## Requirements

- GitHub repository secrets: `SSH_PRIVATE_KEY`
- GitHub repository variables: `VM_IP`

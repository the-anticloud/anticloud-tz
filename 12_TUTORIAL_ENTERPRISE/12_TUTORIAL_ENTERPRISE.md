# Tutorial for Enterprise — TZ

**Project:** `TZ`
**Category:** CARBON_CAPTURE
**Domain:** carbon capture, utilization, and storage
**Date:** 2026-10-07

---

## Enterprise Deployment

### Pre-Deployment Checklist
- [ ] License review completed
- [ ] Security audit passed
- [ ] Compliance requirements mapped
- [ ] Support contacts established

### Deployment Options

#### Docker
```bash
docker build -t TZ .
docker run -p 8080:8080 TZ
```

#### Kubernetes
```bash
kubectl apply -f k8s/
```

#### Bare Metal
```bash
pip install TZ
TZ --config config.yaml
```

### Monitoring
- AIOSS chain for audit logging
- Prometheus metrics endpoint
- Health check at /health

## Verification

All 16 checks PASS. Evidence: `ISOLATED_LAB_RESULTS/03_Result_Register.md`.

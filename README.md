# its-iappa-seed-build-2026-0

Build das imagens da semente **its-iappa-seed** (OpenJarvis 1.0.4 + Ollama + Caddy) em runner limpo do GitHub Actions,
com proveniência e SBOM assinados (artifact attestations). A estação que monta o pendrive só verifica o atestado e
baixa por digest.

- Disparo somente manual (`workflow_dispatch`).
- Sem segredos e sem dados pessoais neste repositório: só o workflow e o patch aplicado ao Dockerfile oficial.
- Ações de terceiros fixadas por SHA completo; commit do OpenJarvis conferido antes do build.

Verificação (exemplo):

```bash
gh attestation verify oci://ghcr.io/iappapedroza/its-iappa-seed-openjarvis@sha256:<digest> \
  --repo iappaPedroza/its-iappa-seed-build-2026-0 \
  --signer-workflow iappaPedroza/its-iappa-seed-build-2026-0/.github/workflows/build.yml
```

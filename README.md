# Azure Federated Identity Credential Abuse

This repo is used to impersonate a User Assigned Managed Identity (UAMI) in Azure using GitHub OIDC federation.

## 🚀 Setup Instructions

1. Inject a Federated Identity Credential into the UAMI:

   - `issuer`: `https://token.actions.githubusercontent.com`
   - `subject`: `repo:<youruser>/<yourrepo>:ref:refs/heads/main`
   - `audiences`: `["api://AzureADTokenExchange"]`

2. Replace these values in `.github/workflows/pwn.yml`:
   - `client-id`
   - `tenant-id`

3. Push to `main` branch and trigger workflow via GitHub UI.

4. You will impersonate the identity and see its access level.

---

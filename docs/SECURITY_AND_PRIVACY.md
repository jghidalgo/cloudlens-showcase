# Security and privacy

## Publicly documented controls

- Customer-owned read-only IAM role
- Unique External ID on role assumption
- Short-lived AWS STS credentials
- Cognito authorization-code flow with PKCE
- Server-side tenant, role, and account authorization
- Tenant-scoped persistence and usage enforcement
- Secrets stored server side rather than in browser or mobile bundles
- Audit records for sensitive administrative and AI operations
- Explicit account and tenant deletion workflows

## Showcase redaction policy

This public repository must not contain:

- AWS access keys, session tokens, secret keys, or private keys
- Stripe secret or webhook keys
- Cognito tokens or client secrets
- External IDs
- Customer resource data or topology snapshots
- Customer email addresses or tenant identifiers
- Production environment files
- CloudFormation outputs containing private operational identifiers

## Responsible disclosure

Do not open a public issue containing a vulnerability, credential, customer identifier, or sensitive log. Report security concerns through the support channel in the live application.

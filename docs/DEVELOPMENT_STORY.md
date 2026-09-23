# Development story

## From topology to a product

CloudLens began with one core idea: an AWS diagram should be derived from the current account rather than maintained manually. The first vertical slice normalized discovered resources and relationships into a graph that could answer deterministic dependency questions.

That foundation expanded into a living operational model:

- Cross-account discovery replaced fixtures with customer-owned read-only roles.
- Scheduled snapshots made infrastructure changes comparable over time.
- Dependency traversal enabled blast-radius and change-risk analysis.
- CloudWatch and security evidence added operational context.
- Cost Explorer data added FinOps opportunities and forecasts.
- Amazon Bedrock turned bounded evidence into readable recommendations and account-aware answers.
- Cognito, tenant isolation, invitations, quotas, deletion workflows, and Stripe billing moved the system toward a pilot-ready SaaS.
- A React Native Android application extended the same tenant and account experience to mobile.

## Important engineering challenges

### Safe cross-account access

CloudLens needed to discover arbitrary customer accounts without requesting access keys. The solution uses customer-deployed IAM roles, a unique External ID, and short-lived STS sessions. The trust relationship remains under the customer's control.

### Evidence-grounded AI

Generic cloud advice is easy to generate but hard to trust. CloudLens first computes normalized facts, dependencies, change evidence, telemetry, and cost summaries. Bedrock then explains those facts while retaining resource references.

### Multi-tenant authorization

Authentication alone is not tenant isolation. The API validates tenant membership, application role, and account grants independently. Data keys and queries remain tenant scoped.

### Shipping the real deployment

The development loop included CloudFormation replacement constraints, IAM permission failures, Cognito session behavior, Bedrock model access, knowledge-base synchronization, PDF output, Stripe webhooks, custom-domain configuration, and Android authentication. The coding agent was used to move between implementation, AWS evidence, and browser/mobile verification.

## Market direction

CloudLens targets small cloud teams, consultants, managed service providers, and growing companies that need architecture visibility without adopting a heavyweight enterprise platform. The initial pilot focuses on understandable inventory, change risk, cost visibility, and actionable AI guidance.

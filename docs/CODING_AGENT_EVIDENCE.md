# Coding-agent connection evidence

## Connection method

The CloudLens coding agent interacted with the AWS delivery workflow through:

- A local AWS-connected development environment for inspection, synthesis, and verification.
- GitHub Actions federation through AWS IAM OIDC.
- The dedicated `CloudLensGitHubDeployRole` for automated deployment.
- AWS CDK and CloudFormation for infrastructure changes.
- AWS service APIs and console verification for runtime troubleshooting.

No long-lived AWS access key is included in this repository or required by the public application.

## Documented activities

The agent helped perform and verify these AWS-connected tasks during development:

1. Synthesized the CDK application and reviewed the generated CloudFormation changes.
2. Configured GitHub Actions to assume the deployment role through OIDC.
3. Diagnosed CloudFormation replacement errors involving custom-named resources.
4. Inspected IAM authorization failures during customer-role onboarding.
5. Validated cross-account `sts:AssumeRole` with an External ID.
6. Inspected Lambda and CloudWatch evidence for failed Bedrock invocations.
7. Verified Cognito callback, logout, group, and token behavior.
8. Configured and tested the Bedrock model and Knowledge Base workflow.
9. Configured Stripe webhook delivery and verified the application lifecycle.
10. Built, deployed, and browser-tested the public application on AWS.

## Verifiable deployment record

The public judge-demo change was committed as `dd37f48` and deployed by GitHub Actions run `#108` on September 22, 2026. The workflow completed successfully in 3 minutes 37 seconds and reported:

- 29 passing test files
- 84 passing tests
- Successful AWS CDK deployment
- AWS data mode enabled
- Successful deployment smoke test
- 4 passing production Playwright tests

The production URL was then verified without authentication at:

https://cloudlens.awsmindset.com/?demo=1

The sanitized workflow structure used for that deployment is published at [deploy-dev.sanitized.yml](deploy-dev.sanitized.yml). Account IDs, role ARNs, certificate identifiers, administrator email addresses, and secret names have been replaced with placeholders.

## Reviewer-safe proof checklist

Screenshots or recordings supplied with the submission should show:

- The coding agent issuing or guiding an AWS-connected deployment/inspection task.
- The resulting AWS CloudFormation, Lambda, Cognito, Bedrock, or CloudWatch state.
- The public CloudLens URL working after deployment.
- Redaction of account IDs where unnecessary, request IDs, tokens, External IDs, ARNs containing sensitive naming, and all secrets.

Operational screenshots are intentionally not committed here until they have been reviewed and redacted.

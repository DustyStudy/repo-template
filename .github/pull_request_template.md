## What and why

<!-- One or two sentences on the change and the reason for it. -->

## How it was tested

<!-- Commands run, CI checks, or the Terraform plan summary. -->

## Checklist

- [ ] No secrets, keys or credentials in the diff (AWS access is OIDC only)
- [ ] New or changed actions are pinned to a full commit SHA
- [ ] Workflow permissions are the minimum needed
- [ ] Terraform changes: `plan` reviewed; nothing applies from this PR

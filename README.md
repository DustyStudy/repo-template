# repo-template

Starting point for new DustyStudy repos. It comes with the security
baseline described in
[BASELINE.md](https://github.com/DustyStudy/DustyStudy/blob/main/BASELINE.md).

## After creating a repo from this template

1. Replace this README.
2. Trim `.github/dependabot.yml` to the ecosystems the repo uses.
3. Terraform repo? Uncomment the `terraform` job in `.github/workflows/ci.yml`
   and set the `AWS_PLAN_ROLE_ARN` repository variable. AWS access is OIDC
   role assumption only; never add access keys. For GovCloud, also change
   `aws-region` to `us-gov-west-1` or `us-gov-east-1`: the example defaults
   to `us-east-1`, which fails against an `arn:aws-us-gov` role.
4. Apply the repo settings and branch ruleset (template repos don't copy
   settings), then again after the first CI run so the scans become
   required checks:

   ```sh
   scripts/repo-baseline.sh <repo>   # in DustyStudy/DustyStudy
   ```

The weekly baseline audit opens an issue if step 4 is missed.

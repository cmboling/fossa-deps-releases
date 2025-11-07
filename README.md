# FOSSA CLI Analysis Workflow

This GitHub Actions workflow automates the analysis of multiple release tags in your repository using the [FOSSA CLI](https://docs.fossa.com/cli/). It checks out your repository, installs the FOSSA CLI, and performs dependency analysis for each specified release tag. Successful analyses are then submitted as releases to FOSSA.

### Inputs

| Input Name     | Required | Description                          | Default Value        |
|----------------|----------|--------------------------------------|--------------------|
| `release_tags` | Yes      | Comma-separated list of release tags to scan | `v3.0.0,v2.0.0`    |

Example:

```yaml
release_tags: v1.0.0,v1.1.0
```

### Notes

- Requires a valid `FOSSA_API_KEY` stored in GitHub Secrets.
- Supports scanning multiple release tags in a single run.
- Non-zero exit codes from `fossa test` do not fail the workflow, allowing analysis to continue for all tags.
